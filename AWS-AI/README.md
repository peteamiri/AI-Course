# AWS Artificial Intelligence — Detailed Course Outline

The Goal of this course is to provide a detailed understanding of AI on Amazon Web Services. 

## Course Goal

By the end of this course, you should be able to:

* Understand the AI/ML/Generative AI landscape on AWS
* Design enterprise AI architectures
* Build machine-learning solutions using AWS services
* Use Amazon SageMaker for the ML lifecycle
* Use Amazon Bedrock for foundation models and generative AI
* Build RAG applications using enterprise data
* Build and deploy AI agents
* Integrate AI with APIs, databases, event systems, and applications
* Apply security, governance, responsible AI, and FinOps
* Design production-grade AI platforms on AWS
* Explain AWS AI architectures at an **Enterprise Architect / Cloud Solution Architect** level

---

# Module 1 — AI Fundamentals

### 1.1 What is Artificial Intelligence?

* AI definition
* AI vs automation
* AI vs traditional programming
* AI capabilities
* AI limitations
* AI use cases

### 1.2 AI Categories

* Narrow AI
* General AI / AGI
* Generative AI
* Predictive AI
* Conversational AI
* Computer vision
* Speech AI
* Recommendation systems

### 1.3 Machine Learning

* Supervised learning
* Unsupervised learning
* Semi-supervised learning
* Reinforcement learning
* Classification
* Regression
* Clustering
* Anomaly detection

### 1.4 Deep Learning

* Neural networks
* CNN
* RNN
* LSTM
* Transformers
* Attention mechanisms

### 1.5 Large Language Models

* Tokens
* Embeddings
* Context windows
* Parameters
* Pre-training
* Fine-tuning
* Instruction tuning
* RLHF
* Inference

---

# Module 2 — AWS AI/ML Ecosystem

Learn how AWS organizes its AI services.

### Core services

* Amazon SageMaker
* Amazon Bedrock
* Amazon Q
* Amazon Comprehend
* Amazon Rekognition
* Amazon Transcribe
* Amazon Polly
* Amazon Translate
* Amazon Textract
* Amazon Lex

### Supporting services

* Amazon S3
* AWS Lambda
* Amazon API Gateway
* Amazon ECS
* Amazon EKS
* Amazon EC2
* Amazon DynamoDB
* Amazon RDS
* Amazon Aurora
* Amazon OpenSearch Service
* Amazon EventBridge
* Amazon SQS
* Amazon SNS
* AWS Step Functions

### Architecture exercise

Design:

> Enterprise AI platform for a government organization using AWS.

---

# Module 3 — AWS AI Architecture

This is particularly important for an Enterprise Architect.

### 3.1 AI reference architecture

Learn the layers:

```text
Users / Applications
        |
        v
API / Application Layer
        |
        v
AI Application
        |
   +----+----+
   |         |
   v         v
Bedrock   SageMaker
   |         |
   v         v
Foundation  ML Models
Models
   |
   v
RAG / Knowledge
   |
   v
Enterprise Data
```

### 3.2 AI architecture patterns

Study:

* AI inference architecture
* Batch inference
* Real-time inference
* RAG architecture
* Fine-tuning architecture
* AI agent architecture
* Event-driven AI
* Multi-model architecture
* Human-in-the-loop architecture

### 3.3 AWS Well-Architected Framework

Apply:

* Operational excellence
* Security
* Reliability
* Performance efficiency
* Cost optimization
* Sustainability

---

# Module 4 — Amazon S3 and AI Data Foundations

AI starts with data.

### Learn

* S3 architecture
* Data lakes
* Data lakehouse concepts
* Data ingestion
* Data classification
* Data lifecycle
* Encryption
* Versioning
* Access control
* Cross-account data access

### AWS services

* Amazon S3
* AWS Glue
* AWS Lake Formation
* Amazon Athena
* AWS DataSync

### Project

Build:

> Enterprise AI Data Lake

```text
Sources
   |
   v
S3 Data Lake
   |
   +--> Glue
   |
   +--> Athena
   |
   +--> Lake Formation
   |
   v
AI / ML
```

---

# Module 5 — Machine Learning on AWS

## 5.1 ML lifecycle

Learn:

```text
Data
  ↓
Preparation
  ↓
Feature Engineering
  ↓
Training
  ↓
Evaluation
  ↓
Model Registry
  ↓
Deployment
  ↓
Inference
  ↓
Monitoring
```

## 5.2 Machine-learning algorithms

Understand:

* Linear regression
* Logistic regression
* Decision trees
* Random forests
* Gradient boosting
* K-means
* Neural networks

You don't need to become a data scientist, but you should understand **when each approach is appropriate**.

---

# Module 6 — Amazon SageMaker

This should be one of the largest modules.

### 6.1 SageMaker overview

* SageMaker Studio
* Notebooks
* Training jobs
* Processing jobs
* Endpoints
* Model registry
* Model monitoring

### 6.2 SageMaker training

Learn:

* Training datasets
* Training containers
* Hyperparameters
* Distributed training
* GPU instances
* Model artifacts

### 6.3 SageMaker deployment

Study:

* Real-time endpoints
* Serverless inference
* Batch transform
* Asynchronous inference
* Multi-model endpoints

### 6.4 SageMaker MLOps

Learn:

* Model pipelines
* CI/CD
* Model registry
* Automated deployment
* Model monitoring
* Data drift
* Model drift

### Project

Build and deploy a complete ML model using SageMaker.

---

# Module 7 — Generative AI Fundamentals

This is the most important modern AI module.

### Learn

* Generative AI architecture
* Foundation models
* LLMs
* Multimodal models
* Prompt engineering
* Embeddings
* Vector search
* RAG
* Fine-tuning
* Model evaluation
* Guardrails

### Understand the difference

```text
Traditional ML
      |
      v
Predict something

Generative AI
      |
      v
Generate something
```

---

# Module 8 — Amazon Bedrock

This should be another major module.

### 8.1 Bedrock architecture

Learn:

* Foundation models
* Model access
* Inference
* Prompt management
* Model customization
* Knowledge Bases
* Agents
* Guardrails

### 8.2 Foundation models

Understand model selection based on:

* Accuracy
* Latency
* Cost
* Context window
* Reasoning capability
* Multimodal capability
* Enterprise requirements

### 8.3 Bedrock inference

Learn:

* Text generation
* Structured output
* Streaming
* Temperature
* Token limits
* System prompts

### Project

Build:

> Enterprise AI chatbot using Amazon Bedrock.

---

# Module 9 — Prompt Engineering

### Prompt architecture

Learn:

* System prompts
* User prompts
* Context
* Instructions
* Examples
* Constraints
* Output schemas

### Techniques

* Zero-shot prompting
* Few-shot prompting
* Chain-of-thought concepts
* ReAct
* Role prompting
* Structured prompting
* Prompt chaining
* Self-evaluation

### Enterprise prompt engineering

* Prompt versioning
* Prompt security
* Prompt injection
* Sensitive-data handling
* Output validation

---

# Module 10 — Retrieval-Augmented Generation

RAG is essential for enterprise AI.

### 10.1 Why RAG?

LLMs don't automatically know your organization's private information.

RAG provides:

```text
User Question
     |
     v
Retrieve Enterprise Data
     |
     v
Relevant Documents
     |
     v
LLM
     |
     v
Answer
```

### 10.2 RAG components

Learn:

* Document ingestion
* Chunking
* Embeddings
* Vector databases
* Similarity search
* Metadata filtering
* Retrieval
* Prompt augmentation
* Generation

### AWS implementation

Study:

* Amazon Bedrock Knowledge Bases
* Amazon OpenSearch
* S3
* Aurora PostgreSQL with vector capabilities
* Other supported vector-store patterns

### Project

Build:

> Enterprise document Q&A system.

For example:

**"Ask questions about 500 pages of enterprise architecture documentation."**

---

# Module 11 — AI Agents

This is particularly valuable for your architecture career.

### What is an AI agent?

Understand:

```text
User
 |
 v
Agent
 |
 +--> Reason
 |
 +--> Retrieve information
 |
 +--> Call API
 |
 +--> Execute action
 |
 +--> Observe result
 |
 +--> Continue
 |
 v
Answer
```

### Learn

* Agent reasoning
* Tools
* Actions
* APIs
* Function calling
* Planning
* Memory
* Context
* Agent orchestration
* Human approval

### Amazon Bedrock Agents

Build agents that can:

* Call APIs
* Query databases
* Retrieve documents
* Execute business processes
* Invoke Lambda functions

### Project

Build:

> Enterprise IT Service Desk AI Agent

Example:

> "Check the status of my application."

Agent:

1. Authenticates user
2. Calls application API
3. Retrieves status
4. Explains result
5. Escalates if necessary

---

# Module 12 — Amazon Q

Study AWS's enterprise-oriented generative AI assistants.

Learn:

* Amazon Q
* Developer assistance
* Business knowledge
* Enterprise data
* Permissions
* Retrieval
* Enterprise productivity

Understand the distinction between:

**Amazon Q vs Amazon Bedrock**

| Capability                   | Bedrock        | Amazon Q      |
| ---------------------------- | -------------- | ------------- |
| Build custom AI applications | Excellent      | Limited       |
| Foundation models            | Yes            | Uses models   |
| RAG                          | Yes            | Yes           |
| Enterprise assistant         | Build yourself | Primary use   |
| AI agents                    | Yes            | Yes           |
| Custom application           | Excellent      | Less flexible |

---

# Module 13 — AI APIs and Application Integration

Learn how AI becomes part of enterprise applications.

### APIs

* REST
* API Gateway
* Lambda
* ECS
* EKS
* Application Load Balancer

### Integration

* EventBridge
* SQS
* SNS
* Step Functions
* Kafka / Amazon MSK

### Example

```text
Salesforce
    |
    v
API Gateway
    |
    v
Lambda
    |
    v
Bedrock
    |
    v
Response
```

---

# Module 14 — AI + Kubernetes

Given your Kubernetes/cloud architecture interests, this is worth studying.

### Learn

* AI workloads on EKS
* GPU workloads
* Kubernetes scheduling
* Model serving
* Containers
* Inference services
* Autoscaling

Architecture:

```text
                EKS
                 |
       +---------+---------+
       |                   |
   AI Service         Model Service
       |                   |
       +---------+---------+
                 |
              Bedrock
                 |
          Foundation Model
```

Understand when to use:

**EKS vs SageMaker vs Bedrock**

---

# Module 15 — Computer Vision

Study AWS computer-vision capabilities.

### Topics

* Image classification
* Object detection
* Facial analysis
* Image moderation
* OCR
* Document analysis

### AWS services

* Amazon Rekognition
* Amazon Textract

### Project

Build:

> Intelligent document processing pipeline.

```text
PDF
 ↓
S3
 ↓
Textract
 ↓
Bedrock
 ↓
Structured Data
 ↓
Database
```

---

# Module 16 — Speech and Conversational AI

### Amazon Transcribe

* Speech-to-text
* Transcription
* Speaker identification
* Medical transcription concepts

### Amazon Polly

* Text-to-speech
* Voice generation

### Amazon Lex

* Conversational interfaces
* Intent recognition
* Slots
* Dialog management

### Project

Build:

> Voice-enabled enterprise assistant.

---

# Module 17 — AI Security

This should be a major Enterprise Architect module.

### AWS security

* IAM
* IAM roles
* IAM policies
* KMS
* Secrets Manager
* VPC
* PrivateLink
* Security groups
* CloudTrail
* GuardDuty

### AI-specific security

Study:

* Prompt injection
* Jailbreaking
* Data leakage
* Model abuse
* Toxic outputs
* Data poisoning
* Model theft
* Unauthorized inference
* Excessive agent permissions

### Zero Trust AI

Apply:

```text
Never Trust
     ↓
Verify
     ↓
Least Privilege
     ↓
Monitor
     ↓
Audit
```

---

# Module 18 — Responsible AI

Study:

* Bias
* Fairness
* Explainability
* Transparency
* Privacy
* Accountability
* Human oversight
* AI governance

### AWS concepts

* SageMaker Clarify
* Model monitoring
* Guardrails
* Evaluation
* Responsible AI practices

---

# Module 19 — AI Governance

Extremely important for enterprise architecture.

Design governance for:

* AI models
* Data
* Prompts
* Agents
* APIs
* Users
* Vendors
* Foundation models

### Create an AI governance framework

```text
AI Governance
 |
 +-- Data Governance
 |
 +-- Model Governance
 |
 +-- Security
 |
 +-- Privacy
 |
 +-- Risk
 |
 +-- Compliance
 |
 +-- Monitoring
 |
 +-- Cost
```

Map this to:

* NIST AI Risk Management Framework
* NIST Cybersecurity Framework
* Zero Trust
* AWS Well-Architected
* Organizational governance

---

# Module 20 — AI Observability and Monitoring

Monitor:

### Infrastructure

* CPU
* Memory
* GPU
* Network

### AI

* Latency
* Token usage
* Model quality
* Hallucination
* Retrieval quality
* Agent failures

### Security

* Prompt attacks
* Unauthorized access
* Data leakage

### Cost

* Tokens
* Model inference
* Storage
* Vector search
* Compute

---

# Module 21 — AI FinOps

Understand:

* Token economics
* Inference costs
* GPU costs
* Model selection
* Batch vs real-time inference
* Caching
* Prompt optimization
* Model routing

### Architecture decision

For each workload ask:

> Should I use Bedrock, SageMaker, EC2, or EKS?

---

# Module 22 — Enterprise AI Architecture Patterns

Develop reusable architecture patterns.

### Pattern 1 — Enterprise Chatbot

```text
User
 ↓
Web Application
 ↓
API Gateway
 ↓
Bedrock
 ↓
Knowledge Base
 ↓
Enterprise Documents
```

### Pattern 2 — RAG

```text
Documents
 ↓
S3
 ↓
Chunking
 ↓
Embeddings
 ↓
Vector Store
 ↓
Retriever
 ↓
LLM
```

### Pattern 3 — AI Agent

```text
User
 ↓
Agent
 ↓
Reason
 ├── Database
 ├── API
 ├── Knowledge Base
 └── Lambda
 ↓
Response
```

### Pattern 4 — AI Data Pipeline

```text
Data Sources
 ↓
Glue
 ↓
S3
 ↓
SageMaker
 ↓
Model
 ↓
Inference
```

---

# Module 23 — Multi-Cloud AI Architecture

Given your AWS/Azure/GCP background, this is a useful advanced topic.

Compare:

| AWS        | Azure            | Google Cloud    |
| ---------- | ---------------- | --------------- |
| Bedrock    | Azure AI Foundry | Vertex AI       |
| SageMaker  | Azure ML         | Vertex AI       |
| S3         | Blob Storage     | Cloud Storage   |
| EKS        | AKS              | GKE             |
| Lambda     | Functions        | Cloud Functions |
| OpenSearch | AI Search        | Vertex Search   |

Study:

* Cloud-neutral AI architecture
* Model portability
* Data portability
* Kubernetes
* API abstraction
* Multi-cloud governance
* Vendor lock-in

---

# Module 24 — Enterprise AI Capstone

The final project should combine everything.

## Project: Enterprise AI Platform

Design an AWS platform for an organization with:

* 100,000+ users
* Multiple business applications
* Large document repositories
* Sensitive information
* Multiple cloud environments
* Existing APIs
* Legacy systems

### Architecture

```text
                    USERS
                      |
                      v
              +---------------+
              | Applications  |
              +-------+-------+
                      |
                      v
                API Gateway
                      |
          +-----------+-----------+
          |                       |
          v                       v
     AI Agents                 AI Apps
          |                       |
          +-----------+-----------+
                      |
                      v
                Amazon Bedrock
                      |
          +-----------+-----------+
          |                       |
          v                       v
      Knowledge Base        Foundation Models
          |
          v
     Enterprise Data
          |
     +----+----+
     |         |
     v         v
     S3      Databases
```

Then add:

* IAM
* KMS
* VPC
* CloudTrail
* Guardrails
* Monitoring
* FinOps
* AI governance
* Disaster recovery
* Multi-region architecture

---

# Recommended Learning Sequence

I would **not** study all of these modules equally.

For an Enterprise Architect, I recommend this priority:

### Tier 1 — Essential

1. AI fundamentals
2. AWS AI ecosystem
3. AWS AI architecture
4. Generative AI
5. Amazon Bedrock
6. Prompt engineering
7. RAG
8. AI agents
9. AI security
10. AI governance

### Tier 2 — Strongly Recommended

11. SageMaker
12. MLOps
13. AI monitoring
14. AI FinOps
15. S3/data architecture
16. API integration
17. Lambda
18. EKS AI architecture

### Tier 3 — Specialized

19. Computer vision
20. Speech AI
21. Conversational AI
22. Advanced model training
23. Multi-cloud AI
24. Advanced deep learning

---

# 16-Week Study Plan

| Week | Focus                        |
| ---- | ---------------------------- |
| 1    | AI/ML fundamentals           |
| 2    | AWS AI services              |
| 3    | AWS AI architecture          |
| 4    | Data engineering for AI      |
| 5    | SageMaker fundamentals       |
| 6    | SageMaker ML/MLOps           |
| 7    | Generative AI                |
| 8    | Amazon Bedrock               |
| 9    | Prompt engineering           |
| 10   | RAG                          |
| 11   | Bedrock Knowledge Bases      |
| 12   | AI agents                    |
| 13   | Amazon Q + enterprise AI     |
| 14   | AI security + responsible AI |
| 15   | AI governance + FinOps       |
| 16   | Enterprise AI capstone       |

---

# The Most Important Architecture Question

As an Enterprise Architect, don't focus only on **"How do I call an LLM?"**

Focus on:

> **"How do I architect, secure, govern, integrate, operate, and scale AI as an enterprise platform?"**

That distinction will make your AWS AI knowledge much more valuable in an **Enterprise Architect / Cloud Solution Architect** interview.

A good target architecture competency is:

**Data → ML → Foundation Models → RAG → Agents → APIs → Security → Governance → Operations → FinOps**

That is the path I would use to take you from **AWS/cloud architecture into AWS AI architecture**.
