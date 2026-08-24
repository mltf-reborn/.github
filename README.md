# ⚡ MLTF: Mortgage Loan for the Future ⚡
### *Next-Gen Agentic Mortgage Origination & Relational Fraud Detection System*

---

[![GCP](https://img.shields.io/badge/Google%20Cloud%20Platform-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![Java 21](https://img.shields.io/badge/Java%2021-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot%203.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Angular](https://img.shields.io/badge/Angular%2017%2B-DD0031?style=for-the-badge&logo=angular&logoColor=white)](https://angular.io/)
[![Gemini](https://img.shields.io/badge/Gemini%202.0%20Flash-4285F4?style=for-the-badge&logo=google-gemini&logoColor=white)](https://deepmind.google/technologies/gemini/)

> **🏆 Hackathon Pitch Tagline:** 
> *Overhauling Malaysia's RM47.3 Billion Mortgage Sector by Bridging Multi-Agent Document Understanding with Google Cloud Spanner Graph Databases to Explode Processing Speeds and Unmask Hidden Fraud-for-Profit Rings.*

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

```
              ┌──────────────────────────────────────────────┐
              │          Angular Web Client Dashboard        │
              │         (Enterprise Angular Material UI)     │
              └──────────────────────┬───────────────────────┘
                                     │
                                     │ HTTPS / REST (Payloads & Events)
                                     ▼
              ┌──────────────────────────────────────────────┐
              │             Orchestrator Service             │
              │      (Java Spring Boot + Google ADK)         │
              └──────────────────────┬───────────────────────┘
                                     │
         ┌───────────────────────────┴───────────────────────────┐
         ▼                           ▼                           ▼
┌─────────────────┐         ┌─────────────────┐         ┌─────────────────┐
│ Perception Agt  │         │ Graph Fraud Agt │         │ Credit Score Agt│
│ Gemini 2.0      │         │ Gemini 1.5 Pro  │         │ Gemini 1.5 Pro  │
│  (Flash Vision) │         │ + Spanner Graph │         │  + CCRIS/CTOS   │
└────────┬────────┘         └────────┬────────┘         └─────────────────┘
         │                           │
         │ (Raw Extraction)          │ (ISO GQL Traversals)
         ▼                           ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                 Google Cloud Spanner (Unified Database)                 │
│      [Relational Tables]  [Dynamic JSON]  [ISO GQL Property Graphs]     │
└────────────────────────────────────┬────────────────────────────────────┘
                                     │
                                     │ Asynchronous Pub/Sub
                                     ▼
                        ┌───────────────────────────┐
                        │   Audit & Compliance Agt  │
                        │   Gemini 2.0 Flash Lite   │
                        │ (PDPA-Compliant JSON Logs)│
                        └───────────────────────────┘
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

```
        [:WORKS_FOR]             [:APPLIES_FOR]
 Employer <─── Applicant ─────────────────────────> Property
                 │
                 ├─[:USES_CONTACT]──> ContactInfo (Phone, Email, IP)
                 │
                 └─[:SUBMITTED]─────> Document (Pay slip, Tax, Valuations)
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
3. **Treatment Validation**: Tested in a laboratory setting using highly realistic simulated synthetic mortgage datasets modeling Malaysian financial dynamics (safeguarding PDPA compliance) [35].

---

*MLTF: Elevating high-stakes mortgage origination into the secure, automated, and interconnected Agentic Era.*
