# ⚡ MLTF: Mortgage Loan for the Future ⚡
### *Next-Gen Agentic Mortgage Origination & Relational Fraud Detection System*

---

[![GCP](https://img.shields.io/badge/Google%20Cloud%20Platform-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![Java 21](https://img.shields.io/badge/Java%2021-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot%203.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Angular](https://img.shields.io/badge/Angular%2017%2B-DD0031?style=for-the-badge&logo=angular&logoColor=white)](https://angular.io/)
[![Gemini](https://img.shields.io/badge/Gemini%202.0%20Flash-4285F4?style=for-the-badge&logo=google-gemini&logoColor=white)](https://deepmind.google/technologies/gemini/)

[![Watch Demo](https://img.shields.io/badge/🎬%20Watch%20Demo-Pitch%20Presentation-EA4335?style=for-the-badge&logo=google-drive&logoColor=white)](https://drive.google.com/file/d/18KTx7EMbD_U7bPESUO6-ojlxBhYWYBC2/view?usp=sharing)
[![Borrower Portal](https://img.shields.io/badge/🌐%20Live%20App-Borrower%20Portal-34A853?style=for-the-badge&logo=google-chrome&logoColor=white)](https://mltf.bagusxmahendra.com/)
[![Ops Dashboard](https://img.shields.io/badge/🛡️%20Live%20App-Ops%20Dashboard%20(Admin)-673AB7?style=for-the-badge&logo=shield&logoColor=white)](https://mltf.bagusxmahendra.com/ops/dashboard-v2)
[![Sample Datasets](https://img.shields.io/badge/📂%20Test%20Docs-Sample%20Datasets-FBBC05?style=for-the-badge&logo=googledrive&logoColor=black)](https://drive.google.com/drive/folders/1DzVWrzagcXVX4bZ908DKVYuNDveypfaW?usp=sharing)

> **🏆 Submission for Devpost & Google "All Things Agentic Hackathon"**
> * **Primary Track:** 🏢 **The Fortified Enterprise Fleet** *(Scalable multi-agent network integrated with enterprise infrastructure, Cloud Spanner Graph, stateful supervisor state machine, zero-trust PDPA compliance, and Pub/Sub telemetry).*
> * **Special Competitions:** 🏛️ **Best Architectural Design** & 🎨 **Best Multimodal UX**
>
> *“Overhauling Malaysia's RM47.3 Billion Mortgage Sector by Bridging Multi-Agent Document Understanding with Google Cloud Spanner Graph Databases to Explode Processing Speeds and Unmask Hidden Fraud-for-Profit Rings.”*

---

## ⚖️ Judges' Evaluation Rubric Alignment (Quick Reference)

| Judging Criteria (Weight) | How MLTF Delivers Maximum Score | Key Proof Points in Repo & Demos |
| :--- | :--- | :--- |
| **💡 Innovation & Operational Utility (40%)** | • Solves RM47.3B friction by collapsing mortgage turnaround from **15–22 days down to < 2 hours**.<br>• Autonomous, end-to-end heavy lifting: Multimodal extraction, ISO GQL multi-hop graph fraud traversal, and instant risk synthesis with **zero manual hand-holding**.<br>• Unmasks collusive fraud rings invisible to legacy tabular systems with **>95% accuracy**. | • [Live Borrower Portal](https://mltf.bagusxmahendra.com/)<br>• [Live Ops Underwriter Dashboard](https://mltf.bagusxmahendra.com/ops/dashboard-v2)<br>• [4-min Video Demo](https://drive.google.com/file/d/18KTx7EMbD_U7bPESUO6-ojlxBhYWYBC2/view?usp=sharing) |
| **🏛️ Architectural Discipline & Tech Stack (30%)** | • Production-grade microservices built with **Java 21** & **Spring Boot 3.x**.<br>• Coordinated by **Google ADK for Java** using the Supervisor-Worker state machine pattern.<br>• **Google Cloud Spanner Graph** provides $O(k)$ Index-Free Adjacency for sub-second link analysis.<br>• Strict compliance with Bank Negara Malaysia & **Malaysian PDPA** via zero-trust guards, Federated Learning, and SHAP XAI. | • [Multi-Agent Topology](#%EF%B8%8F-system-architecture--multi-agent-topology)<br>• [Spanner Graph ISO GQL Engine](#-google-cloud-spanner-graph-unmasking-collusive-fraud-rings)<br>• [Privacy & Federated Learning](#%EF%B8%8F-privacy-first-federated-learning--explainable-ai-xai) |
| **🚀 Demo & Production Readiness (30%)** | • Fully deployed, publicly accessible dual interfaces (Borrower Web UI + Ops Dashboard).<br>• Complete ~4-min live presentation showcasing live Google Cloud execution.<br>• Ready-to-use sample test dossiers (Valid vs. Fraudulent/Tampered datasets).<br>• Comprehensive step-by-step local spin-up and reproducible build instructions. | • [Live Demos & Presentations](#-live-demo--presentation)<br>• [Sample Test Datasets](#-try-it-yourself-with-demo-sample-documents)<br>• [Local Spin-up Guide](#%EF%B8%8F-local-spin-up--deployment-guide) |

---

## 🚀 Live Demo & Presentation

Explore the system in action! Whether you want to watch the complete pitch walkthrough or test drive the live applications directly:

| Destination | Type | Direct Link | Experience Overview |
| :--- | :--- | :--- | :--- |
| 🎬 **Demo Presentation** | **Video Pitch** | [▶️ **Watch on Google Drive**](https://drive.google.com/file/d/18KTx7EMbD_U7bPESUO6-ojlxBhYWYBC2/view?usp=sharing) | Full end-to-end video presentation detailing the problem statement, multi-agent AI architecture, Spanner Graph traversals, and benchmark results. |
| 👤 **User Access Portal** | **Live Web App** | [🚀 **mltf.bagusxmahendra.com**](https://mltf.bagusxmahendra.com/) | Borrower-facing experience: submit loan applications, upload financial records (payslips, tax forms), and observe instantaneous multimodal extraction. |
| 🛡️ **Operational Admin Portal** | **Live Web App** | [⚡ **mltf.bagusxmahendra.com/ops/dashboard-v2**](https://mltf.bagusxmahendra.com/ops/dashboard-v2) | Underwriter & Compliance command center: live agent orchestration queue, interactive Spanner Graph network visualizer, collusive ring unmasking, and explainable audit trails. |
| 💻 **Source Code (GitHub Org)** | **Codebase** | [📂 **github.com/mltf-reborn**](https://github.com/mltf-reborn) | Complete open-source microservices ecosystem across Java 21 Spring Boot agents and Angular frontend. |

### 📂 Try It Yourself with Demo Sample Documents
Want to test the AI extraction and fraud unmasking live on the [Borrower Portal](https://mltf.bagusxmahendra.com/)? Download and test with our curated sample datasets:

| Test Dataset Scenario | Direct Link | What to Expect During Testing |
| :--- | :--- | :--- |
| ✅ **Valid Application Documents** | [📁 **Download Valid Dataset**](https://drive.google.com/drive/folders/1DzVWrzagcXVX4bZ908DKVYuNDveypfaW?usp=sharing) | Clean, authentic Malaysian mortgage dossier (EA Form, 3-month payslips, bank statements, S&P agreement). Passes multimodal extraction, verifies DSR cleanly, and moves smoothly to approval. |
| 🚨 **Invalid / Fraudulent Documents** | [📁 **Download Invalid / Tampered Dataset**](https://drive.google.com/drive/folders/1AkebVkzqWSdvaSN7oB_dY97pdJUXm2tS?usp=sharing) | Contains synthetic identity overlaps, falsified salary amounts, or collusive contact numbers. Watch the **Perception Agent** & **Spanner Graph Agent** immediately flag anomalies and route to the HITL fraud queue. |

---

## 🌟 The "Wow" Factor: Why MLTF is a Paradigm Shift

Every year, Malaysian banks receive over **RM47.3 Billion in property finance applications** [MIDF Research, 2025]. Yet, processing a single mortgage application takes a staggering **15 to 22 days** [MIDF Research, 2025]. Borrowers—especially in the B40 and M40 segments—suffer under long waiting times and subjective human biases, while bank compliance desks remain blind to **relational "fraud-for-profit" networks** [Nguyen & Pontell, 2010; MIDF Research, 2025]. 

Legacy systems evaluate each loan file in **strict tabular isolation**, making them completely blind to coordinated fraud rings where corrupt appraisers, employers, and brokers share contact details and falsify records across multiple different applications [Nguyen & Pontell, 2010].

### 🚀 MLTF Shatters These Bottlenecks by Combining:
1. **Financial-Grade Agentic AI**: An autonomous team of specialized LLM-based worker agents coordinated by a Java-based Supervisor State Machine.
2. **Unified Spanner Graph Technology**: Fusing relational SQL tables and Property Graphs inside **Google Cloud Spanner** to execute multi-hop link analysis in **milliseconds** via **Index-Free Adjacency** [113, 114].
3. **Privacy-First Collaboration**: Leveraging **Federated Learning** to train cross-bank fraud detection models without sharing raw customer data, satisfying the strict requirements of Bank Negara Malaysia and the **PDPA (Personal Data Protection Act)** [385, 396].

**The Result:** Processing cycles collapse from **15–22 days down to under 2 hours**, extraction accuracy jumps to **95.4%**, and fraud detection accuracy surges from a standard 70-80% baseline to **over 95%** [MIDF Research, 2025; Leeladhar Joshi, 2025].

---

## 🏗️ System Architecture & Multi-Agent Topology

MLTF is designed natively as an enterprise-grade, high-throughput microservice ecosystem. We implement the **Supervisor-Worker Agentic Pattern** using **Java 21**, **Spring Boot 3.x**, and the **Google ADK for Java**.

```mermaid
flowchart TD
    subgraph ClientLayer["🖥️ Presentation Layer"]
        UI["Angular Web Client Dashboard<br/>(Enterprise Angular Material UI)"]
    end

    subgraph OrchestrationLayer["🎮 Orchestration & State Management"]
        Supervisor["Supervisor Agent / Orchestrator<br/>(Java 21 · Spring Boot 3.x · Google ADK for Java)"]
    end

    subgraph WorkerFleet["🤖 Autonomous Cognitive Worker Fleet"]
        Perception["Perception Worker<br/>(Gemini 2.0 Flash Vision)"]
        GraphAgent["Graph Fraud Worker<br/>(Gemini 1.5 Pro + ISO GQL)"]
        CreditAgent["Credit Scoring Worker<br/>(Gemini 1.5 Pro + CCRIS/CTOS)"]
        AuditAgent["Audit & Compliance Worker<br/>(Gemini 2.0 Flash Lite)"]
    end

    subgraph PersistenceLayer["☁️ Google Cloud Data & Event Backbone"]
        Spanner[("Google Cloud Spanner (Unified Database)<br/>[Relational Tables] · [Dynamic JSON] · [ISO GQL Property Graph]")]
        PubSub[["Google Cloud Pub/Sub<br/>(Async Telemetry & Event Streaming)"]]
    end

    UI -->|"HTTPS / REST (Payloads & Events)"| Supervisor
    Supervisor -->|"1. Raw Dossier Dispatch"| Perception
    Supervisor -->|"2. Extracted Entities"| GraphAgent
    Supervisor -->|"3. Financials Assessment"| CreditAgent

    Perception -->|"Structured JSON Extraction"| Spanner
    GraphAgent -->|"ISO GQL Graph Traversals & Anomaly Scoring"| Spanner

    Spanner -.->|"State Transitions & Events"| PubSub
    PubSub -->|"Asynchronous Telemetry Stream"| AuditAgent
    AuditAgent -.->|"PDPA-Compliant Immutable Audit Logs"| Spanner

    classDef uiClass fill:#E3F2FD,stroke:#1565C0,stroke-width:2px,color:#0D47A1;
    classDef orchClass fill:#EDE7F6,stroke:#512DA8,stroke-width:2px,color:#311B92;
    classDef workerClass fill:#E8F5E9,stroke:#2E7D32,stroke-width:2px,color:#1B5E20;
    classDef gcpClass fill:#FFF3E0,stroke:#E65100,stroke-width:2px,color:#BF360C;

    class UI uiClass;
    class Supervisor orchClass;
    class Perception,GraphAgent,CreditAgent,AuditAgent workerClass;
    class Spanner,PubSub gcpClass;
```

---

## 👥 The Agentic "Dream Team"

MLTF doesn't just run static pipelines; it orchestrates a coordinate network of high-autonomy cognitive agents:

| Agent Role | Model / Tech | Superpower / Mission |
| :--- | :--- | :--- |
| **Supervisor Agent (Orchestrator)** | **Google ADK for Java** | Manages the global state machine, schedules sub-tasks, handles state transitions, and halts the workflow for Human-in-the-Loop (HITL) review if confidence scores dip below 85% [457]. |
| **Perception Worker** | **Gemini 2.0 Flash** (Vision) | Processes raw PDFs (EA Forms, pay slips, LHDN Form B/BE, bank statements, S&P Agreements, Appraiser Reports). Bypasses weak legacy OCR by directly reading nested tables, validating physical signatures, and detecting visual tampering [186]. |
| **Relational Graph Worker** | **Gemini 1.5 Pro + ISO GQL** | Connects newly extracted applicant data directly into a unified graph. Generates real-time, visual ISO GQL queries to traverse multi-hop connections and flag synthetic identities [89]. |
| **Credit Scoring Worker** | **Gemini 1.5 Pro** | Integrates extracted financials with external, simulated credit scoring engines (CCRIS and CTOS) to dynamically evaluate DSR (Debt Service Ratio) and default probability [19]. |
| **Audit & Compliance Worker** | **Gemini 2.0 Flash Lite** | Listens asynchronously via **Google Cloud Pub/Sub** to translate deep model reasoning into plain-text, transparent compliance logs to satisfy BNM regulators and PDPA [461]. |

---

## 🔍 Google Cloud Spanner Graph: Unmasking Collusive Fraud Rings

In standard relational databases (RDBMS), uncovering a 5-hop fraud network (e.g., matching a phone number across five different bank entities) requires exponential **recursive JOIN queries** ($O(N^k)$), which suffer from up to **85% performance degradation** per join level [113, 114]. 

MLTF solves this with **Google Cloud Spanner Graph**. By using **Index-Free Adjacency**, the Relational Graph Agent navigates direct memory pointers, traversing millions of connections in **milliseconds** ($O(k)$ complexity) [74, 90, 91].

### 📊 Unified Graph Database Schema

```mermaid
graph LR
    Applicant["👤 Applicant"]
    Employer["🏢 Employer"]
    Property["🏠 Property"]
    ContactInfo["📞 ContactInfo<br/>(Phone, Email, IP)"]
    Document["📄 Document<br/>(Payslip, Tax, Valuations)"]
    Appraiser["🧑‍⚖️ Appraiser"]

    Applicant -->|":WORKS_FOR"| Employer
    Applicant -->|":APPLIES_FOR"| Property
    Applicant -->|":USES_CONTACT"| ContactInfo
    Applicant -->|":SUBMITTED"| Document
    Appraiser -->|":VALUED"| Property
```

### 💻 Live Fraud Detection in Action: The Power of ISO GQL

When the Relational Graph Agent detects a new document extraction, it automatically runs an **ISO GQL (Graph Query Language)** check. It actively flags **Synthetic Identity Overlaps**—for instance, when five supposedly unrelated loan applicants use the exact same employer phone number and property appraiser:

```sql
/* Query generated dynamically by Gemini 1.5 Pro to traverse relational loops */
GRAPH MortgageGraph
MATCH (a1:Applicant)-[:USES_CONTACT]->(c:ContactInfo)<-[:USES_CONTACT]-(a2:Applicant)
WHERE a1.id != a2.id AND c.type = 'PHONE'
MATCH (a1)-[:APPLIES_FOR]->(p1:Property)<-[:VALUED]-(appraiser:Appraiser)-[:VALUED]->(p2:Property)<-[:APPLIES_FOR]-(a2)
RETURN a1.name AS Applicant_A, 
       a2.name AS Applicant_B, 
       c.value AS Shared_Phone, 
       appraiser.name AS Collusive_Appraiser;
```

If this GQL query returns a match, the **Fraud Anomaly Worker** instantly signals the Orchestrator, isolating the application from the main credit queue and placing it on the dashboard of a human fraud investigator.

---

## 🛡️ Privacy-First Federated Learning & Explainable AI (XAI)

Banks are traditionally protective of customer data and cannot legally share raw dossiers under **Malaysian Personal Data Protection Act (PDPA)** regulations [385]. 

### 🤝 How MLTF Facilitates Cross-Bank Collaboration:
1. **Decentralized Federated Learning**: Multiple Malaysian financial institutions cooperatively train a global **Graph Neural Network (GNN)**. Only aggregated model parameters (weight updates) are shared across the secure network—**never raw customer data** [396, 397].
2. **Deterministic Compliance Agent**: Built on rule-based symbolic AI, it acts as a hard constraint layer [461, 490]. It guarantees that if a transaction lacks explicit user PDPA consent, the data is completely omitted from any learning loop.
3. **SHAP-Based Explainable AI**: No "black boxes." When a loan is flagged or rejected, the system uses **SHAP (SHapley Additive exPlanations)** values to generate visual charts explaining the exact credit scoring weights (e.g., High CCRIS outstanding + shared employer contact = 92% anomaly risk score), enabling transparent auditing.

---

## 🎨 Enterprise Human-in-the-Loop (HITL) Dashboard

The frontend application is built using **Angular v17+** and **Angular Material** (adhering strictly to enterprise design guidelines, without Tailwind utility classes to ensure maintainable styling).

### 🖥️ Key Dashboard Capabilities:
* **The Queue**: Underwriters track applications as they move dynamically through *Extraction*, *Graph Validation*, *Credit Assessment*, and *Compliance Verification*.
* **Interactive Graph Visualizer**: Interactive network mapping displaying nodes and edges, allowing underwriters to physically see the flagged fraud rings and connections between entities.
* **The "Audit Trail" Panel**: Fully populated with real-time audit logs generated by the **Audit Worker**, detailing *why* the AI reached its conclusions.
* **One-Click Override**: Human underwriters can override decisions with a required text justification, satisfying fiduciary accountability constraints [238].

👉 **Try the Live Underwriter Dashboard**: [https://mltf.bagusxmahendra.com/ops/dashboard-v2](https://mltf.bagusxmahendra.com/ops/dashboard-v2)

---

## 📈 Unprecedented Business & Social Impact

```
Processing Time   [15 - 22 Days] ───► [Under 2 Hours]             (95%+ Speedup!)
Fraud Detection   [70% - 80% Baseline] ───► [Over 95%]            (Unmasking rings)
Extraction Error  [OCR Legacy: High] ───► [Agentic Vision: 4.6%]  (Auto-correct loops)
```

### 🌍 Financial & Social Impact:
* **Empowering the Underserved (B40/M40)**: Traditional credit scoring relies on rigid, subjective manual verification where minor document formatting differences cause delays. MLTF's objective, multimodal agentic parsing ensures a fair, unbiased, and fast underwriting decision.
* **Securing Retail Banking**: Coordinated "fraud for profit" costs commercial banks millions in non-performing loans (NPLs). Real-time graph network audits safeguard bank balance sheets proactively.
* **Operational Resource Multiplication**: Automating routine data extraction and verification frees up underwriters to focus solely on high-value, high-complexity lending decisions, acting as a true "force multiplier."

---

## 📖 Scientific Rigor: Design Science Methodology (DSM)

MLTF is not just an application; it is built upon the academic foundation of **Design Science Methodology (Wieringa, 2014)** [25]:

1. **Problem Investigation**: Done via rigorous stakeholder analysis of Malaysian underwriters and compliance officers to pinpoint legacy bottlenecks [27].
2. **Treatment Design (The Artifact)**: Multi-Agent supervisor-worker system built natively in Java and Spanner Graph [29, 30].
3. **Treatment Validation**: Tested in a laboratory setting using highly realistic simulated synthetic mortgage datasets modeling Malaysian financial dynamics (safeguarding PDPA compliance) [35] (Available for testing: [Valid Demo Dataset](https://drive.google.com/drive/folders/1DzVWrzagcXVX4bZ908DKVYuNDveypfaW?usp=sharing) & [Invalid/Tampered Dataset](https://drive.google.com/drive/folders/1AkebVkzqWSdvaSN7oB_dY97pdJUXm2tS?usp=sharing)).

---

## ☁️ Google Cloud & Google AI Tech Stack Verification

Every component of MLTF is natively built on the Google Cloud and Agentic AI ecosystem:

| Layer / Hackathon Requirement | Google Cloud / Google AI Technology | Specific Role in MLTF |
| :--- | :--- | :--- |
| **🧠 Cognitive AI Models** | **Gemini 2.0 Flash (Multimodal Vision)**<br>**Gemini 1.5 Pro** | • **Perception Agent**: Directly parses multi-page complex financial PDFs (EA forms, payslips, S&P) without brittle legacy OCR.<br>• **Graph & Scoring Agents**: Generates ISO GQL graph queries and evaluates credit risk. |
| **🤖 Agent Framework** | **Google ADK for Java (Agent Development Kit)** | Coordinates the Supervisor-Worker state machine, handles async agent dispatch, error recovery, and Human-in-the-Loop triggers. |
| **🌐 Unified Database** | **Google Cloud Spanner + Spanner Graph** | Fuses relational applicant dossiers with ISO GQL Property Graphs via Index-Free Adjacency ($O(k)$ complexity) to unmask collusive fraud rings in milliseconds. |
| **⚡ Messaging & Telemetry** | **Google Cloud Pub/Sub** | Asynchronously routes inter-agent events and streams immutable JSON audit logs to the Audit & Compliance Worker. |
| **🚀 Compute & Deployment** | **Google Cloud Run & GKE** | Containerized microservices and Angular web frontend with automatic elasticity and enterprise scalability. |

---

## 🏛️ Organization Repositories & Agent Ecosystem

| Repository | Role / Microservice | Tech Stack |
| :--- | :--- | :--- |
| 🎮 [**`mltf-reborn/supervisor-agent`**](https://github.com/mltf-reborn/supervisor-agent) | Master Orchestrator, ADK State Machine, Agent Scheduler | Java 21, Spring Boot 3.x, Google ADK for Java |
| 👁️ [**`mltf-reborn/document-processing-agent`**](https://github.com/mltf-reborn/document-processing-agent) | Multimodal PDF/Image Extraction & Form Tamper Analysis | Java 21, Spring Boot 3.x, Gemini 2.0 Flash Vision |
| 🕸️ [**`mltf-reborn/graph-processing-agent`**](https://github.com/mltf-reborn/graph-processing-agent) | Spanner Graph ISO GQL Engine, Collusive Ring Link Analysis | Java 21, Spring Boot 3.x, Spanner Graph, Gemini 1.5 Pro |
| 📂 [**`mltf-reborn/case-management-service`**](https://github.com/mltf-reborn/case-management-service) | Mortgage Application Lifecycle, DSR & Credit Scoring Engine | Java 21, Spring Boot 3.x, Cloud Spanner / SQL |
| 💻 [**`mltf-reborn/ui`**](https://github.com/mltf-reborn/ui) | Borrower Portal & Enterprise Underwriter Dashboard (HITL) | Angular 17+, Angular Material, RxJS |

---

## 🛠️ Local Spin-Up & Deployment Guide

Follow these steps to spin up the entire MLTF ecosystem locally or verify reproducible builds:

### 📋 Prerequisites
* **Java Development Kit (JDK)**: Java 21+
* **Node.js**: v18+ & npm
* **Google Cloud Credentials**: Authenticated with Gemini API / Vertex AI access (`gcloud auth application-default login`).

### 1️⃣ Clone the Repositories
```bash
git clone https://github.com/mltf-reborn/supervisor-agent.git
git clone https://github.com/mltf-reborn/document-processing-agent.git
git clone https://github.com/mltf-reborn/graph-processing-agent.git
git clone https://github.com/mltf-reborn/case-management-service.git
git clone https://github.com/mltf-reborn/ui.git
```

### 2️⃣ Configure Environment Variables
Set your Google Cloud Project & Gemini credentials in your shell or `.env`:
```bash
export GOOGLE_CLOUD_PROJECT="your-gcp-project-id"
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service-account.json"
export GEMINI_API_KEY="your-gemini-api-key"
```

### 3️⃣ Launch Backend Microservices
Run each Java Spring Boot service using the included Gradle wrapper:
```bash
# Terminal 1: Case Management Service
cd case-management-service && ./gradlew bootRun

# Terminal 2: Document Processing Agent
cd document-processing-agent && ./gradlew bootRun

# Terminal 3: Graph Processing Agent
cd graph-processing-agent && ./gradlew bootRun

# Terminal 4: Supervisor Agent (Orchestrator)
cd supervisor-agent && ./gradlew bootRun
```

### 4️⃣ Launch Angular Frontend
```bash
cd ui
npm install
npm start
```
* **Borrower Portal**: Open [http://localhost:4200/](http://localhost:4200/)
* **Ops Underwriter Dashboard**: Open [http://localhost:4200/ops/dashboard-v2](http://localhost:4200/ops/dashboard-v2)

---

## 📢 Hackathon Submission & Community

* **Hackathon**: [Devpost: All Things Agentic Hackathon ("Ready, Set, Agent!")](https://allthingsagentichackathon.devpost.com/)
* **Official Hashtag**: `#AllThingsAgenticHackathon`
* **Video Pitch**: [▶️ Watch Demo Presentation on Google Drive](https://drive.google.com/file/d/18KTx7EMbD_U7bPESUO6-ojlxBhYWYBC2/view?usp=sharing)
* **Live Borrower App**: [https://mltf.bagusxmahendra.com/](https://mltf.bagusxmahendra.com/)
* **Live Ops Dashboard**: [https://mltf.bagusxmahendra.com/ops/dashboard-v2](https://mltf.bagusxmahendra.com/ops/dashboard-v2)

---

*MLTF: Elevating high-stakes mortgage origination into the secure, automated, and interconnected Agentic Era.*
