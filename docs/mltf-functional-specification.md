# FUNCTIONAL SPECIFICATION DOCUMENT (v3)
## Project MLTF: Mortgage Loan for the Future (Automated Agentic Underwriting & Relational Graph Fraud Analytics)

---

## 1. Authenticate User
```mermaid
sequenceDiagram
    autonumber

    actor User as User

    box LightBlue Client Side (MLTF)
        participant Frontend as mltf_frontend<br/>(Auth0 SDK)
    end

    box LightYellow Identity Providers
        participant Auth0 as Auth0<br/>Authorization Server
        participant Google as Google IDP
    end

    box LightGreen Secure Backend (MLTF)
        participant Backend as Spring Boot API
    end

    %% 1. Initiate Authentication
    Note over User,Backend: 1. Initiate Authentication
    User->>Frontend: Click "Login with Google"
    activate Frontend
    Frontend->>Frontend: Generate PKCE Pair<br/>(Code Verifier & Code Challenge)
    Frontend->>User: Redirect to Auth0 /authorize<br/>(client_id, code_challenge, redirect_uri)
    deactivate Frontend

    %% 2. Identity Federation via Google
    Note over User,Backend: 2. Identity Federation via Google
    User->>Auth0: Present credentials / Request Authorization
    activate Auth0
    Auth0->>User: Display login choices
    User->>Auth0: Select "Continue with Google"
    Auth0->>Google: Redirect to Google Accounts
    activate Google
    Google->>User: Prompt for Google Login & Consent
    User-->>Google: Approve authentication
    Google->>Auth0: Return Auth Code to Auth0 callback
    deactivate Google

    %% 3. Token Exchange (PKCE Verification)
    Note over User,Backend: 3. Token Exchange (PKCE Verification)
    Auth0->>Frontend: Redirect to MLTF callback_url<br/>with Auth Code
    deactivate Auth0
    activate Frontend

    Frontend->>Auth0: POST /oauth/token<br/>(auth_code, code_verifier, client_id)
    activate Auth0
    Auth0->>Auth0: Verify code_verifier against<br/>original code_challenge
    Auth0-->>Frontend: Return Tokens (ID Token & Access Token JWT)
    deactivate Auth0

    Frontend->>Frontend: Store Access Token safely in memory
    Frontend->>User: Redirect to MLTF Dashboard (Authenticated)
    deactivate Frontend

    %% 4. Propagating JWT to MLTF Secure Resources
    Note over User,Backend: 4. Propagating JWT to MLTF Secure Resources
    User->>Frontend: Click "Start KYC Upload" (Step 2)
    activate Frontend
    Frontend->>Backend: GET /api/v1/kyc/status<br/>Headers: [Authorization: Bearer [JWT]]
    activate Backend
    Backend->>Backend: Intercept Request<br/>Validate JWT signature via Auth0 JWKS
    Backend-->>Frontend: Return KYC Status (200 OK)
    deactivate Backend
    Frontend->>User: Render KYC Upload Interface
    deactivate Frontend
```
## 2. eKYC Process
```mermaid
sequenceDiagram
    autonumber

    actor User as User

    box LightBlue Client Side (MLTF)
        participant Frontend as mltf-frontend
    end

    box LightGreen Secure Backend (MLTF)
        participant Backend as supervisor-agent<br/>(Gemini 2.0 Flash)
        participant CaseService as case-management-service
        participant DB as Database
        participant DocAgent as document-processing-agent<br/>(Gemini 2.0 Flash)
    end

    box LightYellow Cloud Infrastructure
        participant GCS as Google Cloud Storage<br/>(GCS)
    end

    box Silver Third-Party Services
        participant KYCService as National KYC Service<br/>(e.g., JPN / Bureau)
    end

    box Lavender Operations & Compliance
        participant OpsDashboard as operational-dashboard
        actor Underwriter as Ops Team
    end

    %% 1. Check Existing KYC Status
    Note over User,Underwriter: 1. Check Existing KYC Status
    User->>Frontend: Navigate to Profile/KYC section
    activate Frontend
    Frontend->>Backend: GET /api/v1/kyc/status
    activate Backend
    Backend->>DB: Query KYC status for current user
    activate DB
    DB-->>Backend: Return current status (e.g., PENDING or NONE)
    deactivate DB
    Backend-->>Frontend: Return 200 OK { status: "PENDING" }
    deactivate Backend
    Frontend-->>User: Display KYC Introduction / Status Screen
    deactivate Frontend

    %% 2. Navigate to KYC Screen
    Note over User,Underwriter: 2. Navigate to KYC Screen
    User->>Frontend: Click on "Start KYC Process"
    activate Frontend
    Frontend->>Frontend: Redirect to KYC Screen
    Frontend-->>User: Render KYC Upload Interface<br/>(Front/Back NRIC + Camera Capture)
    deactivate Frontend

    %% 3. Secure Document & Selfie Ingestion
    Note over User,Underwriter: 3. Secure Document & Selfie Ingestion
    User->>Frontend: Upload ID Document (Front & Back) and Take Selfie
    activate Frontend
    Frontend->>Backend: POST /api/v1/kyc/verify<br/>Payload: [Multipart NRIC, Selfie Image]
    activate Backend

    Note over Backend,GCS: Storage Phase [Upload raw images to secure bucket]
    Backend->>GCS: Upload NRIC & Selfie to bucket/session-id
    activate GCS
    GCS-->>Backend: Return Secure File URLs
    deactivate GCS

    %% 4. Multimodal Analysis & Extraction
    Note over User,Underwriter: 4. Multimodal Analysis & Extraction
    Note over Backend,DocAgent: Document Verification Phase [Agentic Deep Check]
    Backend->>DocAgent: Execute Tampering, Extraction & Face Match Check<br/>(Pass File URLs)
    activate DocAgent
    DocAgent->>DocAgent: Perform pixel-level analysis for tampering<br/>(Check metadata, borders, compression)
    DocAgent->>DocAgent: Perform Biometric Face Match (Selfie vs NRIC photo)<br/>& Liveness Check
    DocAgent->>DocAgent: Extract fields (ID No, Full Name, DOB, Address)<br/>Calculate Extraction Confidence Score
    DocAgent-->>Backend: Return Payload: [Is_Tampered: False, Face_Match: 95%, Fields, Conf_Score: 0.96]
    deactivate DocAgent

    %% 5. External Verification Registry Check
    Note over User,Underwriter: 5. External Verification Registry Check
    Note over Backend,KYCService: External Registry Phase
    Backend->>KYCService: Query National Registry<br/>Payload: [Document ID, Full Name]
    activate KYCService
    KYCService-->>Backend: Return Detailed KYC Record<br/>(Sanctions list check, PEP status, blacklist status)
    deactivate KYCService

    %% 6. Automated Scoring & Escalation Gate
    Note over User,Underwriter: 6. Automated Scoring & Escalation Gate (Database State Management)
    Backend->>Backend: Calculate KYC Final Score<br/>(Combine Extraction, Face Match, Tampering & Registry Output)

    alt KYC Score is BORDERLINE (e.g. 70% - 85% or minor visual mismatch)
        Note over Backend,Underwriter: Asynchronous Human-in-the-Loop (HITL) Handling
        
        %% Update DB and tell user it's pending
        Backend->>DB: UPDATE kyc_status = 'PENDING_REVIEW'
        Backend-->>Frontend: Return 202 Accepted [KYC Status: PENDING_REVIEW]
        Frontend-->>User: Display "Application Under Review" Screen
        
        %% Step 1 & 2: Call Case Management & Create Case
        Backend->>CaseService: POST /api/v1/cases (Send all case details & URLs)
        activate CaseService
        CaseService->>CaseService: Create new case & Assign to Ops Team
        
        %% Step 3: Ops Team Notification
        CaseService-->>OpsDashboard: Push Notification / WebSocket [New Case Assigned]
        deactivate CaseService

        Note over OpsDashboard,Underwriter: Later: Asynchronous Human Review Process
        activate Underwriter
        
        %% Step 4: Ops Team reviews and decides
        Underwriter->>OpsDashboard: Open case details
        activate OpsDashboard
        Underwriter->>OpsDashboard: Review extracted fields, NRIC, selfie & Submit Decision (Approve/Reject)
        OpsDashboard->>CaseService: POST /api/v1/cases/{id}/decision
        activate CaseService
        
        %% Step 5: Case Updated
        CaseService->>CaseService: Update Case Status (Resolved)
        
        %% Step 6: KYC Updated
        CaseService->>Backend: Internal Event/Webhook: Case Resolved (Decision)
        activate Backend
        Backend->>DB: UPDATE kyc_status = 'APPROVED' or 'REJECTED'
        deactivate Backend
        
        CaseService-->>OpsDashboard: Return 200 OK [Case Updated]
        deactivate CaseService
        OpsDashboard-->>Underwriter: Display Success/Next Case
        deactivate OpsDashboard
        deactivate Underwriter

    else KYC Score is ABOVE or BELOW borderline (Auto-Decision)
        alt Score is ABOVE Borderline (Clear Pass)
            Backend->>DB: UPDATE kyc_status = 'APPROVED'
            Backend-->>Frontend: Return 200 OK [KYC Status: Approved]
            Frontend-->>User: Display "KYC Success" (Navigate to Step 3)
        else Score is BELOW Borderline (Clear Fail / Tampered Doc)
            Backend->>DB: UPDATE kyc_status = 'REJECTED'
            Backend-->>Frontend: Return 400 Bad Request [KYC Status: Rejected]
            Frontend-->>User: Display "KYC Failed" (Provide retry instructions)
        end
    end
    
    deactivate Backend
    deactivate Frontend
```
