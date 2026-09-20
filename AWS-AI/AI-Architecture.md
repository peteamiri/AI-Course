
# AI Architectures — Detailed Course Module

**AI architecture** is one of the most important topics for an Enterprise Architect because it connects AI models to the broader enterprise: data, applications, APIs, security, governance, infrastructure, operations, and business processes.


## 1. What is AI Architecture?

**AI architecture** is the design of the technology components, data flows, models, applications, infrastructure, security controls, and operational processes required to build and run an AI system.

A traditional application architecture might look like:

```text
Users
  ↓
Web / Mobile Application
  ↓
API Layer
  ↓
Business Logic
  ↓
Database
```

An AI application introduces additional architectural components:

```text
Users
  ↓
AI Application
  ↓
AI Orchestration
  ↓
AI Model
  ↓
Enterprise Data / Knowledge
  ↓
Data Platform
```

But an enterprise AI architecture is considerably broader:

```text
                 ┌─────────────────────────┐
                 │        USERS            │
                 │ Employees / Customers   │
                 └────────────┬────────────┘
                              │
                              ▼
                 ┌─────────────────────────┐
                 │   AI APPLICATIONS       │
                 │ Chatbots / Copilots     │
                 │ Decision Support        │
                 │ Intelligent Apps        │
                 └────────────┬────────────┘
                              │
                              ▼
                 ┌─────────────────────────┐
                 │ AI ORCHESTRATION        │
                 │ Prompts / RAG / Agents  │
                 │ Tool Calling            │
                 └────────────┬────────────┘
                              │
              ┌───────────────┼────────────────┐
              ▼               ▼                ▼
        ┌──────────┐    ┌───────────┐    ┌──────────┐
        │Foundation│    │ ML Models │    │AI APIs   │
        │ Models   │    │           │    │Services  │
        └────┬─────┘    └─────┬─────┘    └──────────┘
             │                │
             └────────┬───────┘
                      ▼
             ┌─────────────────┐
             │ Enterprise Data │
             │ S3 / DB / Lake  │
             │ Documents / APIs │
             └────────┬────────┘
                      ▼
             ┌─────────────────┐
             │ Data Engineering │
             │ ETL / Catalog    │
             │ Governance       │
             └─────────────────┘

     Security / Governance / Monitoring
              across ALL layers
```

The key Enterprise Architect principle is:

> **AI architecture is not just model architecture. It is an enterprise architecture containing AI capabilities.**

---

# 2. The AI Architecture Stack

A useful way to understand AI architecture is through layers.

```text
┌──────────────────────────────────────────────┐
│  LAYER 8 — BUSINESS / USER EXPERIENCE       │
│  Copilots, assistants, intelligent apps     │
├──────────────────────────────────────────────┤
│  LAYER 7 — AI AGENTS / ORCHESTRATION        │
│  Planning, tools, workflows, function calls │
├──────────────────────────────────────────────┤
│  LAYER 6 — GENERATIVE AI                     │
│  LLMs, multimodal models, foundation models │
├──────────────────────────────────────────────┤
│  LAYER 5 — ML / DEEP LEARNING                │
│  Prediction, classification, forecasting    │
├──────────────────────────────────────────────┤
│  LAYER 4 — KNOWLEDGE / RAG                   │
│  Embeddings, vector search, enterprise data │
├──────────────────────────────────────────────┤
│  LAYER 3 — DATA PLATFORM                     │
│  Data lakes, databases, ETL, catalogs       │
├──────────────────────────────────────────────┤
│  LAYER 2 — COMPUTE / AI INFRASTRUCTURE       │
│  GPUs, CPUs, containers, Kubernetes         │
├──────────────────────────────────────────────┤
│  LAYER 1 — SECURITY / NETWORK / GOVERNANCE   │
│  IAM, encryption, Zero Trust, compliance    │
└──────────────────────────────────────────────┘
```

Security and governance should actually be viewed as **cross-cutting concerns**, rather than merely Layer 1.

---

# 3. Traditional ML Architecture

The first architecture you should understand is a conventional machine-learning architecture.

For example, suppose an organization wants to predict whether a customer will cancel a service.

```text
                DATA SOURCES
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
   CRM Data      Transactions   Web Data
       │             │             │
       └─────────────┼─────────────┘
                     ▼
             ┌──────────────┐
             │ Data Lake    │
             │ S3           │
             └──────┬───────┘
                    ▼
             ┌──────────────┐
             │ ETL /        │
             │ Data Prep     │
             └──────┬───────┘
                    ▼
             ┌──────────────┐
             │ Feature       │
             │ Engineering   │
             └──────┬───────┘
                    ▼
             ┌──────────────┐
             │ ML Training   │
             │ SageMaker     │
             └──────┬───────┘
                    ▼
             ┌──────────────┐
             │ Model         │
             │ Registry      │
             └──────┬───────┘
                    ▼
             ┌──────────────┐
             │ Model         │
             │ Deployment    │
             └──────┬───────┘
                    ▼
              Prediction API
                    │
                    ▼
              Business App
```

This architecture is primarily about:

**Data → Features → Model → Prediction**

---

# 4. ML Training Architecture

Training architecture and inference architecture should be treated separately.

## Training

```text
Raw Data
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Training Dataset
   ↓
Training Job
   ↓
Model Evaluation
   ↓
Model Registry
```

The training environment may require substantial compute.

For large models:

```text
             Training Dataset
                    │
                    ▼
             ┌──────────────┐
             │ Distributed  │
             │ Training     │
             └──────┬───────┘
                    │
          ┌─────────┼─────────┐
          ▼         ▼         ▼
        GPU 1     GPU 2     GPU 3
          │         │         │
          └─────────┼─────────┘
                    ▼
             Trained Model
```

---

# 5. ML Inference Architecture

Once a model has been trained, applications need to use it.

```text
Application
     │
     ▼
API Gateway
     │
     ▼
Inference Service
     │
     ▼
ML Model
     │
     ▼
Prediction
     │
     ▼
Application
```

For example:

```text
Customer Information
       ↓
   ML Model
       ↓
Churn Probability = 0.82
       ↓
Business Rule
       ↓
Retention Action
```

This introduces an important architectural distinction:

### Training

Expensive, periodic, compute-intensive.

### Inference

Frequent, latency-sensitive, production-oriented.

---

# 6. Generative AI Architecture

Generative AI changes the architecture substantially.

A simple LLM architecture is:

```text
User
 │
 ▼
Application
 │
 ▼
Prompt
 │
 ▼
Foundation Model
 │
 ▼
Generated Response
 │
 ▼
User
```

For AWS, a typical architecture might use:

```text
User
 ↓
Web / Mobile Application
 ↓
API Gateway
 ↓
Lambda / ECS / EKS
 ↓
Amazon Bedrock
 ↓
Foundation Model
 ↓
Response
```

The application does **not necessarily need to train the model itself**.

That is one of the major differences between traditional ML and modern generative AI architectures.

---

# 7. RAG Architecture

One of the most important enterprise AI architectures is **Retrieval-Augmented Generation (RAG)**.

The problem:

> An LLM does not automatically know an organization's private documents, databases, policies, procedures, or current information.

RAG addresses this by retrieving relevant enterprise information before asking the model to generate an answer.

## RAG architecture

```text
                 USER
                   │
                   ▼
             AI Application
                   │
                   ▼
             User Question
                   │
                   ▼
             Query Embedding
                   │
                   ▼
          ┌──────────────────┐
          │ Vector Search    │
          │ / Knowledge Base │
          └────────┬─────────┘
                   │
             Relevant Chunks
                   │
                   ▼
             Prompt Assembly
                   │
                   ▼
          ┌──────────────────┐
          │ Foundation Model │
          └────────┬─────────┘
                   │
                   ▼
              Answer
```

The data ingestion side looks like:

```text
Documents
   │
   ▼
S3
   │
   ▼
Document Processing
   │
   ▼
Chunking
   │
   ▼
Embeddings
   │
   ▼
Vector Database
```

At runtime:

```text
Question
   ↓
Embedding
   ↓
Vector Search
   ↓
Relevant Documents
   ↓
Prompt + Documents
   ↓
LLM
   ↓
Grounded Answer
```

---

# 8. Why RAG Is So Important

Consider an organization's internal policy:

> "Employees must submit travel expenses within 10 business days."

The LLM by itself may not know this policy.

With RAG:

```text
User:
"What is the deadline for travel expenses?"

          ↓

Vector Search

          ↓

Travel Policy Document

          ↓

Relevant text inserted into prompt

          ↓

LLM

          ↓

"Travel expenses must be submitted
within 10 business days."
```

This is called **grounding**.

RAG therefore separates:

**Model intelligence**

from

**Enterprise knowledge**

That is a very important architecture principle.

---

# 9. Agentic AI Architecture

The next level is an **AI agent**.

A conventional LLM:

```text
Question
   ↓
LLM
   ↓
Answer
```

An agent:

```text
                    ┌─────────────┐
                    │    LLM      │
                    │ Reasoning   │
                    └──────┬──────┘
                           │
             ┌─────────────┼──────────────┐
             ▼             ▼              ▼
          Search         API          Database
          Tool           Tool           Tool
             │             │              │
             └─────────────┼──────────────┘
                           ▼
                       Results
                           │
                           ▼
                       LLM
                           │
                           ▼
                         Action
```

An agent can:

1. Understand a goal.
2. Break it into tasks.
3. Retrieve information.
4. Call tools.
5. Analyze results.
6. Make decisions.
7. Execute actions.
8. Verify results.

---

# 10. Enterprise Agent Architecture

A more realistic enterprise architecture looks like:

```text
                   Employee
                      │
                      ▼
                AI Assistant
                      │
                      ▼
              Agent Orchestrator
                      │
             ┌────────┼────────┐
             ▼        ▼        ▼
           RAG       LLM      Memory
             │        │
             │        │
             └────────┼─────────┐
                      │         │
                      ▼         ▼
                   Tools      Policies
                      │
          ┌───────────┼────────────┐
          ▼           ▼            ▼
        CRM          ERP          HR
        API          API          API
          │           │            │
          └───────────┼────────────┘
                      ▼
                  Business
                   Systems
```

The architecture becomes much closer to an **enterprise integration architecture**.

That is where your existing enterprise architecture experience becomes especially valuable.

---

# 11. AI + API Architecture

AI should generally not have unrestricted access to enterprise systems.

Instead:

```text
AI Agent
   │
   ▼
Policy / Authorization Layer
   │
   ▼
API Gateway
   │
   ▼
Enterprise APIs
   │
   ├── CRM
   ├── ERP
   ├── HR
   ├── Finance
   └── Procurement
```

For example:

```text
Agent:
"Create a purchase order."

       ↓

Authorization

       ↓

Purchase Order API

       ↓

ERP

       ↓

Approval Workflow

       ↓

Purchase Order Created
```

This is much safer than giving an LLM direct database access.

---

# 12. AI + Data Lake Architecture

Enterprise AI depends heavily on data architecture.

A typical AWS architecture could look like:

```text
              Enterprise Data Sources
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
      ERP            CRM           Documents
        │              │              │
        └──────────────┼──────────────┘
                       ▼
                 Amazon S3
                       │
                       ▼
               Data Lake
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       ETL/ELT      Catalog      Quality
          │
          ▼
       Curated Data
          │
     ┌────┴─────────┐
     ▼              ▼
 Traditional ML   Generative AI
     │              │
     ▼              ▼
 Predictions       RAG
```

This illustrates an important concept:

> **AI architecture starts with data architecture.**

Poor data architecture generally produces poor AI.

---

# 13. Multimodal AI Architecture

Modern foundation models can process multiple modalities.

For example:

* Text
* Images
* Audio
* Video
* Documents
* Structured data

Architecture:

```text
                   User
                     │
             ┌───────┼────────┐
             ▼       ▼        ▼
           Text    Image     Audio
             │       │        │
             └───────┼────────┘
                     ▼
              Multimodal Model
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
        Text       Image      Action
       Output      Output
```

An enterprise example:

```text
Invoice Image
      ↓
Document AI
      ↓
Extract Fields
      ↓
Validation
      ↓
LLM Reasoning
      ↓
ERP API
      ↓
Accounts Payable
```

---

# 14. Document AI Architecture

A very useful enterprise architecture is:

```text
PDF / Image / Scan
       ↓
Document Storage
       ↓
OCR / Document Extraction
       ↓
Structured Information
       ↓
Validation
       ↓
Database
       ↓
RAG / ML / Workflow
```

AWS provides services such as Amazon Textract for document analysis.

This architecture is extremely useful for:

* invoices
* contracts
* forms
* financial documents
* government documents
* applications
* reports

---

# 15. Conversational AI Architecture

A chatbot architecture can be:

```text
User
 ↓
Web / Mobile / Voice
 ↓
Conversation Layer
 ↓
Intent / LLM
 ↓
RAG
 ↓
Enterprise Knowledge
 ↓
Response
```

A more advanced version:

```text
User
 ↓
Conversation Interface
 ↓
LLM
 ↓
Agent
 ├── Knowledge Base
 ├── Customer API
 ├── Order API
 ├── Payment API
 └── Support System
 ↓
Response
```

This changes a chatbot from:

> "answering questions"

into:

> **performing business processes.**

---

# 16. AI Architecture with Kubernetes

For organizations using Kubernetes:

```text
                    Users
                      │
                      ▼
                API Gateway
                      │
                      ▼
                  EKS
                      │
       ┌──────────────┼──────────────┐
       ▼              ▼              ▼
 AI Application   RAG Service   Agent Service
       │              │              │
       └──────────────┼──────────────┘
                      ▼
                Model Gateway
                      │
             ┌────────┼─────────┐
             ▼        ▼         ▼
          Bedrock   SageMaker  External
                              Models
```

Kubernetes can provide:

* container orchestration
* scaling
* service discovery
* deployment automation
* isolation
* portability
* observability

This can be particularly useful in multi-cloud environments.

---

# 17. Hybrid AI Architecture

Large enterprises often need hybrid architecture.

```text
                    Enterprise
                        │
            ┌───────────┴───────────┐
            │                       │
       On-Premises                 AWS
            │                       │
      ┌─────┼─────┐         ┌──────┼──────┐
      │     │     │         │      │      │
     DB    ERP   Files     S3   Bedrock SageMaker
      │                       │      │
      └───────────┬───────────┘      │
                  │                  │
              Secure Network         │
                  │                  │
                  └────────┬─────────┘
                           ▼
                      AI Platform
```

Connectivity could involve:

* Direct Connect
* VPN
* private APIs
* Transit Gateway
* VPC endpoints
* Zero Trust controls

---

# 18. Multi-Cloud AI Architecture

An enterprise may want:

```text
                  AI Application
                        │
                  AI Abstraction
                       Layer
                        │
        ┌───────────────┼────────────────┐
        ▼               ▼                ▼
       AWS             Azure             GCP
    Bedrock          Azure AI          Vertex AI
    SageMaker        Services           Services
        │               │                │
        └───────────────┼────────────────┘
                        ▼
                 Enterprise Data
```

An **AI abstraction layer** can prevent application code from being tightly coupled to a single model provider.

For example:

```text
Application
    ↓
AI Gateway
    ↓
Model Router
    ├── Model A
    ├── Model B
    ├── Model C
    └── Model D
```

The router can select a model based on:

* cost
* latency
* capability
* security
* region
* availability
* data classification

---

# 19. AI Security Architecture

Security must be built into every layer.

```text
                USERS
                  │
             Authentication
                  │
                  ▼
             Authorization
                  │
                  ▼
             AI Application
                  │
             Input Security
                  │
                  ▼
              AI Gateway
                  │
        ┌─────────┼─────────┐
        ▼         ▼         ▼
       RAG       Agent      LLM
        │         │         │
        ▼         ▼         ▼
      Data      APIs      Model
```

Important AI-specific threats include:

### Prompt injection

An attacker manipulates instructions given to an AI system.

### Data leakage

Sensitive information is returned to an unauthorized user.

### Model manipulation

Attackers attempt to influence model behavior.

### Excessive agent permissions

An agent receives more privileges than it needs.

### Insecure tool use

The model calls a business API with dangerous parameters.

### Data poisoning

Training or knowledge data is manipulated.

---

# 20. Zero Trust AI Architecture

Given an enterprise security environment, you can apply Zero Trust principles to AI.

Instead of:

```text
AI Agent
   ↓
Trusted
   ↓
Everything
```

Use:

```text
AI Agent
   ↓
Authenticate
   ↓
Authorize
   ↓
Policy Evaluation
   ↓
Least Privilege
   ↓
Specific API
   ↓
Specific Data
   ↓
Audit
```

Every tool invocation should potentially be:

```text
WHO?
WHAT?
WHY?
WHICH DATA?
WHICH ACTION?
IS IT AUTHORIZED?
```

This becomes particularly important with autonomous agents.

---

# 21. AI Governance Architecture

Enterprise AI requires governance.

```text
                    AI GOVERNANCE
                         │
       ┌─────────────────┼─────────────────┐
       ▼                 ▼                 ▼
    Security          Privacy          Compliance
       │                 │                 │
       ▼                 ▼                 ▼
     Model            Data             Regulatory
     Risk             Risk               Risk
       │                 │                 │
       └─────────────────┼─────────────────┘
                         ▼
                    AI Systems
```

Governance should cover:

* model approval
* data classification
* privacy
* security
* explainability
* bias
* model risk
* human oversight
* auditability
* retention
* regulatory requirements
* third-party models
* model/version management

---

# 22. AI Observability Architecture

Production AI requires observability.

Traditional application monitoring:

```text
CPU
Memory
Latency
Errors
Availability
```

AI requires additional measurements:

```text
                 AI OBSERVABILITY
                        │
       ┌────────────────┼────────────────┐
       ▼                ▼                ▼
 Infrastructure       Model            Business
    Metrics          Metrics            Metrics
       │                │                │
       ▼                ▼                ▼
 CPU / Memory       Accuracy          Outcomes
 Latency            Drift             Revenue
 Errors             Hallucination     Productivity
                    Toxicity          User feedback
```

For GenAI, you may monitor:

* token consumption
* latency
* model response quality
* hallucination rate
* retrieval quality
* prompt quality
* grounding
* cost per request
* failed tool calls
* agent execution time

---

# 23. AI FinOps Architecture

AI can become expensive very quickly.

A useful architecture includes:

```text
AI Application
      │
      ▼
AI Gateway
      │
      ├── Model
      ├── Token Usage
      ├── Requests
      └── Latency
      │
      ▼
Cost Monitoring
      │
      ▼
FinOps
```

You can implement policies such as:

```text
Simple request
      ↓
Small / inexpensive model

Complex reasoning
      ↓
More capable model

Very complex task
      ↓
Premium model
```

This is called **model routing**.

---

# 24. Event-Driven AI Architecture

AI can also be integrated with event-driven architectures.

```text
Business Event
      │
      ▼
EventBridge / Kafka
      │
      ▼
AI Processing
      │
      ▼
Model
      │
      ▼
Decision
      │
      ▼
Business Event
```

For example:

```text
New Customer Complaint
        ↓
      Event
        ↓
       AI
        ↓
Sentiment + Classification
        ↓
High Priority?
     /       \
   Yes        No
   ↓           ↓
Escalate     Normal Queue
```

This integrates AI with existing enterprise integration patterns.

---

# 25. Batch AI Architecture

Not every AI workload requires real-time inference.

For example:

```text
Millions of Records
       ↓
Batch Processing
       ↓
ML Model
       ↓
Predictions
       ↓
Data Warehouse
       ↓
Business Intelligence
```

Use batch processing when latency is not critical.

Examples:

* nightly forecasting
* fraud analysis
* customer segmentation
* document processing
* recommendation generation

---

# 26. Real-Time AI Architecture

For latency-sensitive applications:

```text
User
 ↓
API Gateway
 ↓
Application
 ↓
AI Model
 ↓
Response
```

The architecture may need:

* low-latency networking
* caching
* model optimization
* provisioned capacity
* asynchronous processing where possible
* streaming responses

---

# 27. Human-in-the-Loop Architecture

For high-risk decisions, AI should not operate completely autonomously.

```text
AI
 ↓
Recommendation
 ↓
Human Review
 ↓
Approve / Reject
 ↓
Business System
```

For example:

```text
AI detects potentially fraudulent transaction
                    ↓
              Risk Score
                    ↓
              Human Analyst
                /       \
            Approve     Reject
```

This is especially appropriate for:

* financial decisions
* healthcare
* legal decisions
* security operations
* government decisions
* employment decisions

---

# 28. Autonomous AI Architecture

At the other extreme:

```text
                  GOAL
                   │
                   ▼
                 AGENT
                   │
              ┌────┴────┐
              ▼         ▼
           PLAN       MEMORY
              │
              ▼
             TOOL
              │
              ▼
           OBSERVE
              │
              ▼
           EVALUATE
              │
         ┌────┴────┐
         ▼         ▼
       Done       Retry
         │
         ▼
       RESULT
```

This is substantially more complex than a chatbot.

The Enterprise Architect must consider:

* authorization
* state management
* failure recovery
* transaction boundaries
* idempotency
* human approval
* audit
* rollback
* tool security
* runaway execution
* cost controls

---

# 29. The AI Reference Architecture

A useful enterprise reference architecture combines all of these concepts:

```text
┌─────────────────────────────────────────────────────────┐
│                     BUSINESS USERS                      │
│ Employees | Customers | Partners | Operations          │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                 AI APPLICATION LAYER                    │
│ Copilots | Chatbots | Intelligent Applications         │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│               AI ORCHESTRATION LAYER                    │
│ Prompting | RAG | Agents | Tool Calling | Memory       │
└───────────────┬──────────────┬──────────────┬───────────┘
                │              │              │
                ▼              ▼              ▼
        ┌────────────┐ ┌────────────┐ ┌────────────┐
        │ Foundation │ │ ML Models  │ │ AI APIs    │
        │ Models     │ │            │ │            │
        └─────┬──────┘ └─────┬──────┘ └────────────┘
              │              │
              └──────┬───────┘
                     ▼
┌─────────────────────────────────────────────────────────┐
│                    KNOWLEDGE LAYER                      │
│ Vector DB | Search | Knowledge Graph | Enterprise Data │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                     DATA PLATFORM                       │
│ S3 | Data Lake | Databases | ETL | Catalog | Governance │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                  INFRASTRUCTURE                         │
│ EC2 | EKS | ECS | Lambda | GPU | Networking             │
└─────────────────────────────────────────────────────────┘

   SECURITY | IAM | ENCRYPTION | ZERO TRUST | GOVERNANCE
   OBSERVABILITY | AUDIT | COMPLIANCE | FINOPS
```

This is the architecture I would recommend you learn as your **primary Enterprise AI reference architecture**.

---

# 30. Mapping the Architecture to AWS

The architecture maps naturally to AWS services:

| Architecture capability    | AWS examples                                                |
| -------------------------- | ----------------------------------------------------------- |
| Foundation models          | Amazon Bedrock                                              |
| ML platform                | Amazon SageMaker                                            |
| Enterprise AI assistants   | Amazon Q                                                    |
| Object/data lake           | Amazon S3                                                   |
| Data integration           | AWS Glue                                                    |
| Data governance            | AWS Lake Formation                                          |
| Search/vector capabilities | Amazon OpenSearch Service and other supported vector stores |
| Compute                    | EC2, ECS, EKS, Lambda                                       |
| APIs                       | API Gateway                                                 |
| Events                     | EventBridge                                                 |
| Streaming                  | Amazon MSK / streaming services                             |
| Documents                  | Amazon Textract                                             |
| Vision                     | Amazon Rekognition                                          |
| Speech-to-text             | Amazon Transcribe                                           |
| Text-to-speech             | Amazon Polly                                                |
| NLP                        | Amazon Comprehend                                           |
| Identity                   | IAM                                                         |
| Encryption                 | KMS                                                         |
| Network security           | VPC, security controls                                      |
| Auditing                   | CloudTrail                                                  |
| Monitoring                 | CloudWatch                                                  |
| Secrets                    | Secrets Manager                                             |

---

# 31. The Most Important Architectural Patterns

For your AWS Enterprise Architect course, I would prioritize these **10 AI architecture patterns**:

### Pattern 1 — Traditional ML

```text
Data → Features → Training → Model → Prediction
```

### Pattern 2 — Generative AI

```text
Application → Bedrock → Foundation Model → Response
```

### Pattern 3 — RAG

```text
Question → Retrieval → Enterprise Data → LLM → Answer
```

### Pattern 4 — Agentic AI

```text
Goal → Agent → Reason → Tools → Observe → Act
```

### Pattern 5 — AI + APIs

```text
AI → Authorization → API Gateway → Business Systems
```

### Pattern 6 — Multimodal AI

```text
Text + Image + Audio + Documents → AI Model
```

### Pattern 7 — Event-driven AI

```text
Event → AI → Decision → Event → Business Process
```

### Pattern 8 — Human-in-the-loop

```text
AI → Recommendation → Human → Action
```

### Pattern 9 — Hybrid/Multi-cloud AI

```text
Enterprise → AI Abstraction → AWS/Azure/GCP/On-Prem
```

### Pattern 10 — Enterprise AI Platform

```text
                    AI PLATFORM
                         │
      ┌──────────────────┼──────────────────┐
      ▼                  ▼                  ▼
   Models              Data             Agents
      │                  │                  │
      └──────────────────┼──────────────────┘
                         ▼
                   Applications
                         │
             ┌───────────┼───────────┐
             ▼           ▼           ▼
          Security   Governance    FinOps
```

---

# 32. How an Enterprise Architect Should Think About AI

The most important shift is to stop thinking:

> **"Which AI model should I use?"**

and instead ask:

### Business

**What business capability are we improving?**

### Data

**What data does the AI require?**

### Model

**Do we need traditional ML, an LLM, a multimodal model, or an agent?**

### Knowledge

**Does the model need enterprise knowledge through RAG?**

### Integration

**What systems must the AI interact with?**

### Security

**What can the AI see and what can it do?**

### Governance

**Who is accountable for the AI decision?**

### Operations

**How will we evaluate and monitor it?**

### Economics

**What will each AI transaction cost?**

### Resilience

**What happens when the model, API, retrieval system, or agent fails?**

That gives you a much more powerful architecture framework:

```text
             BUSINESS OBJECTIVE
                    ↓
                  DATA
                    ↓
              AI CAPABILITY
                    ↓
              MODEL / RAG
                    ↓
             ORCHESTRATION
                    ↓
               INTEGRATION
                    ↓
                SECURITY
                    ↓
               GOVERNANCE
                    ↓
             OPERATIONS
                    ↓
                 FINOPS
```

## 33. The architecture hierarchy you should master

For your AWS AI course, I recommend learning AI architecture in this order:

```text
1. AI Architecture Fundamentals
             ↓
2. ML Architecture
             ↓
3. AWS ML Architecture / SageMaker
             ↓
4. Generative AI Architecture
             ↓
5. Bedrock Architecture
             ↓
6. Prompt Engineering
             ↓
7. RAG Architecture
             ↓
8. Vector / Knowledge Architecture
             ↓
9. AI Agent Architecture
             ↓
10. AI + API / Microservices Architecture
             ↓
11. Multimodal AI
             ↓
12. Event-Driven AI
             ↓
13. Kubernetes AI Architecture
             ↓
14. Hybrid / Multi-Cloud AI
             ↓
15. AI Security / Zero Trust
             ↓
16. AI Governance
             ↓
17. AI Observability / Evaluation
             ↓
18. AI FinOps
             ↓
19. Enterprise AI Reference Architecture
             ↓
20. AI Architecture Capstone
```

**For an Enterprise Architect, the highest-value concepts are #4–#10 and #14–#19.** Those are where AI intersects most strongly with cloud architecture, enterprise integration, security, governance, and operating models.
