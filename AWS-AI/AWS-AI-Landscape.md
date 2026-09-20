# AI / ML / Generative AI Landscape on AWS

The AWS AI landscape is easiest to understand as a **stack of capabilities**, rather than as a list of AWS services.

At the highest level:

```text
                         ENTERPRISE AI APPLICATIONS
              ┌─────────────────────────────────────────┐
              │ Chatbots │ Copilots │ Agents │ Analytics │
              └───────────────────┬─────────────────────┘
                                  │
                    GENERATIVE AI PLATFORM
              ┌───────────────────┴─────────────────────┐
              │              Amazon Bedrock              │
              │ Foundation Models │ RAG │ Agents │      │
              │ Guardrails │ Evaluation │ Customization │
              └───────────────────┬─────────────────────┘
                                  │
                         MACHINE LEARNING
              ┌───────────────────┴─────────────────────┐
              │             Amazon SageMaker             │
              │ Data │ Training │ Models │ MLOps │       │
              │ Deployment │ Monitoring │ Governance     │
              └───────────────────┬─────────────────────┘
                                  │
                         AI SERVICES / APIs
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
   Vision                    Language                   Speech
 Rekognition               Comprehend                 Transcribe
 Textract                  Translate                   Polly
        │                         │                         │
        └─────────────────────────┬─────────────────────────┘
                                  │
                         DATA & INFRASTRUCTURE
              ┌───────────────────┴─────────────────────┐
              │ S3 │ Databases │ EKS │ EC2 │ Lambda     │
              │ Glue │ Lake Formation │ OpenSearch      │
              └─────────────────────────────────────────┘
```

The key architectural distinction is:

> **Traditional AI services solve specific AI problems; ML platforms let you build/train models; Generative AI platforms let you build applications around foundation models.**

---

# 1. First: AI, ML, and Generative AI Are Not the Same Thing

## Artificial Intelligence

**Artificial Intelligence (AI)** is the broadest category.

AI attempts to make computer systems perform tasks that normally require some degree of human intelligence.

Examples:

* Understanding language
* Recognizing objects
* Predicting events
* Detecting fraud
* Recommending products
* Understanding speech
* Generating text
* Making decisions
* Automating workflows

So:

```text
AI
│
├── Machine Learning
│
├── Deep Learning
│
├── Computer Vision
│
├── Natural Language Processing
│
├── Speech
│
├── Generative AI
│
└── AI Agents
```

---

# 2. Machine Learning

**Machine Learning (ML)** is a subset of AI.

Instead of explicitly programming every rule, you provide data and allow an algorithm/model to learn patterns.

Traditional programming:

```text
Rules + Data
     ↓
Program
     ↓
Result
```

Machine learning:

```text
Data + Expected Results
          ↓
       Training
          ↓
         Model
          ↓
       Prediction
```

For example, suppose you want to predict whether a financial transaction is fraudulent.

The model could learn from:

* Transaction amount
* Location
* Time
* Merchant
* Customer behavior
* Historical fraud patterns

The output might be:

```text
Fraud probability = 94%
```

This is fundamentally different from asking an LLM to generate an explanation.

---

# 3. Deep Learning

Deep learning uses neural networks with multiple layers.

A simplified architecture is:

```text
Input
  ↓
Neural Network
  ↓
Hidden Layers
  ↓
More Hidden Layers
  ↓
Output
```

Deep learning is heavily used for:

* Computer vision
* Speech recognition
* Natural-language processing
* Recommendation systems
* Generative AI

Modern foundation models are largely based on deep-learning architectures, particularly **Transformers**.

---

# 4. Generative AI

Generative AI is AI that can **generate new content**.

Examples:

* Text
* Code
* Images
* Audio
* Video
* Structured data

Traditional ML might answer:

> "Is this transaction fraudulent?"

Generative AI might answer:

> "Explain why this transaction appears suspicious and summarize the relevant evidence."

The distinction is important:

| Traditional ML    | Generative AI      |
| ----------------- | ------------------ |
| Predict           | Generate           |
| Classification    | Text generation    |
| Regression        | Code generation    |
| Forecasting       | Summarization      |
| Anomaly detection | Question answering |
| Fraud detection   | Conversational AI  |

---

# 5. Where AWS Fits

AWS provides several different layers for AI.

Think of AWS AI as approximately five major architectural categories:

### Layer 1 — Prebuilt AI services

You consume AI through APIs.

### Layer 2 — Machine-learning platform

You build and operate your own ML models.

### Layer 3 — Foundation-model platform

You consume and customize foundation models.

### Layer 4 — Generative AI applications

You build RAG applications, copilots and agents.

### Layer 5 — Infrastructure

You build AI workloads directly on AWS compute, storage, networking and Kubernetes.

---

# 6. AWS Prebuilt AI Services

AWS provides managed AI capabilities where you don't necessarily need to train your own model.

Important services include:

### Amazon Rekognition

Computer vision.

Examples:

* Image analysis
* Object detection
* Video analysis
* Content moderation

Architecture:

```text
Application
     ↓
Rekognition API
     ↓
AWS AI Model
     ↓
Analysis
```

---

# 7. Amazon Textract

Textract extracts information from documents.

For example:

```text
PDF
 │
 ▼
Textract
 │
 ├── Text
 ├── Tables
 ├── Forms
 └── Key/value pairs
```

This becomes particularly powerful when combined with Generative AI.

For example:

```text
Invoice
 ↓
S3
 ↓
Textract
 ↓
Structured information
 ↓
Bedrock
 ↓
Invoice analysis
```

---

# 8. Amazon Transcribe

Speech-to-text.

Example:

```text
Audio
 ↓
Transcribe
 ↓
Text
 ↓
Bedrock
 ↓
Summary / Analysis
```

This enables applications such as:

* Call-center analysis
* Meeting transcription
* Voice assistants
* Customer-service analytics

---

# 9. Amazon Polly

Polly performs the reverse operation:

```text
Text
 ↓
Polly
 ↓
Speech
```

It provides text-to-speech capabilities.

---

# 10. Amazon Comprehend

Amazon Comprehend provides natural-language processing capabilities.

It can be used for tasks such as:

* Entity recognition
* Sentiment analysis
* Key phrase extraction
* Language detection
* Document classification

Historically, services such as Comprehend represented the **pre-generative-AI AWS NLP model**.

Today, you should understand both approaches:

```text
Comprehend
   ↓
Specific NLP task

Bedrock
   ↓
General-purpose foundation model
```

---

# 11. Amazon Translate

Machine translation:

```text
English
 ↓
Translate
 ↓
French / Spanish / Arabic / etc.
```

It is useful when translation is a specific application requirement and you don't need a general-purpose LLM.

---

# 12. Amazon Lex

Lex is used to build conversational interfaces.

Conceptually:

```text
User
 ↓
Speech/Text
 ↓
Lex
 ↓
Intent
 ↓
Business Logic
 ↓
Response
```

It is particularly useful for structured conversational workflows.

---

# 13. Amazon SageMaker — The ML Platform

This is where the AWS landscape becomes much more sophisticated.

**Amazon SageMaker** is AWS's major managed platform for building, training, deploying, and operating machine-learning models.

Think of SageMaker as the **ML engineering and lifecycle platform**.

---

# 14. SageMaker ML Lifecycle

A typical lifecycle looks like:

```text
               DATA
                 │
                 ▼
          Data Preparation
                 │
                 ▼
        Feature Engineering
                 │
                 ▼
             Training
                 │
                 ▼
          Model Evaluation
                 │
                 ▼
          Model Registry
                 │
                 ▼
           Deployment
                 │
                 ▼
            Inference
                 │
                 ▼
            Monitoring
                 │
                 └──────────────┐
                                │
                                ▼
                         Retraining
```

This is a classic **MLOps lifecycle**.

---

# 15. SageMaker vs Bedrock

This is one of the most important AWS AI distinctions to understand.

### SageMaker

Think:

> **"I want to build and operate machine-learning models."**

### Bedrock

Think:

> **"I want to build applications using foundation models."**

Simplified:

```text
SageMaker
   |
   +-- Data
   +-- Training
   +-- Fine-tuning
   +-- Models
   +-- Deployment
   +-- MLOps
   +-- Monitoring


Bedrock
   |
   +-- Foundation Models
   +-- Prompting
   +-- RAG
   +-- Agents
   +-- Guardrails
   +-- Model evaluation
   +-- GenAI applications
```

There is overlap, but the architectural intent is different.

---

# 16. Foundation Models

A **Foundation Model (FM)** is a large model trained on broad datasets that can subsequently be adapted for many applications.

Examples include models capable of:

* Text generation
* Summarization
* Question answering
* Code generation
* Reasoning
* Image generation
* Multimodal processing

Instead of training an enormous model yourself, you can consume a foundation model through a managed AWS service.

This is one of the major reasons **Amazon Bedrock** is important.

---

# 17. Amazon Bedrock

For modern AWS Generative AI architecture, Bedrock is probably the most important service to learn.

Think of it as:

> **A managed platform for building generative-AI applications using foundation models.**

Conceptually:

```text
                  Amazon Bedrock
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
   Foundation       RAG/KB         Agents
     Models            │              │
        │              │              │
        └──────────────┼──────────────┘
                       │
                       ▼
                 AI Application
```

---

# 18. Foundation Models Through Bedrock

Bedrock provides access to multiple foundation-model families rather than forcing you to build a single model architecture.

This is strategically important.

Your application can be designed around an abstraction layer:

```text
                  Application
                       |
                       ▼
                   Bedrock
                       |
          ┌────────────┼────────────┐
          ▼            ▼            ▼
        Model A      Model B      Model C
```

This allows an organization to evaluate models based on:

* Accuracy
* Cost
* Latency
* Context length
* Reasoning
* Modality
* Security
* Availability

rather than hard-coding the application around one model.

---

# 19. Prompt Engineering

A prompt is the instruction/context supplied to a model.

Basic:

```text
Summarize this document.
```

Enterprise prompt:

```text
You are an enterprise financial analyst.

Analyze the following document.

Requirements:
1. Identify financial risks.
2. Identify compliance issues.
3. Provide supporting evidence.
4. Return the answer as JSON.
5. Do not invent information.
```

Prompt engineering becomes an important application-development discipline.

---

# 20. Embeddings

Embeddings convert information into numerical vectors.

Conceptually:

```text
"Enterprise architecture"
          ↓
     Embedding Model
          ↓
[0.23, -0.81, 0.44, ...]
```

Documents and queries can therefore be represented mathematically.

This enables semantic search.

For example:

```text
User:
"What is our cloud security policy?"

              ↓

          Embedding

              ↓

      Vector Search

              ↓

Relevant documents
```

This is fundamental to **RAG**.

---

# 21. Retrieval-Augmented Generation

RAG is one of the most important Generative AI architectures.

Instead of relying entirely on the model's pretrained knowledge:

```text
Question
   ↓
LLM
   ↓
Answer
```

you retrieve enterprise information first:

```text
                    User
                      │
                      ▼
                  Question
                      │
                      ▼
                  Retrieval
                      │
                      ▼
              Enterprise Data
                      │
                      ▼
              Relevant Context
                      │
                      ▼
                Foundation Model
                      │
                      ▼
                   Answer
```

This allows an organization to use its own:

* Policies
* Documents
* Manuals
* Databases
* Knowledge bases
* Architecture documents
* Contracts
* Technical documentation

without necessarily retraining the foundation model on all that information.

---

# 22. Amazon Bedrock Knowledge Bases

Bedrock provides managed capabilities for building knowledge-base/RAG solutions.

A conceptual architecture is:

```text
Documents
   ↓
S3
   ↓
Knowledge Base
   ↓
Chunking
   ↓
Embeddings
   ↓
Vector Store
   ↓
Retrieval
   ↓
Foundation Model
   ↓
Answer
```

This is extremely important for enterprise applications.

---

# 23. AI Agents

The next evolution beyond simple RAG applications is **AI agents**.

A conventional chatbot:

```text
Question
 ↓
LLM
 ↓
Answer
```

An agent can:

```text
User
 ↓
Agent
 ↓
Reason about task
 ↓
Select tool
 ↓
Call API
 ↓
Retrieve information
 ↓
Perform action
 ↓
Evaluate result
 ↓
Continue / finish
```

For example:

> "Find why my application failed and open a service ticket if necessary."

An agent might:

1. Query the application database
2. Examine logs
3. Search documentation
4. Identify the problem
5. Call the service-management API
6. Create a ticket
7. Return the ticket number

That is substantially more powerful than simple question answering.

---

# 24. Bedrock Agents

Bedrock provides managed capabilities for creating agents.

A conceptual architecture:

```text
                     User
                       │
                       ▼
                     Agent
                       │
            ┌──────────┼──────────┐
            ▼          ▼          ▼
        Knowledge     API       Lambda
          Base        Calls
            │          │          │
            └──────────┼──────────┘
                       ▼
                  Foundation
                    Model
                       │
                       ▼
                    Result
```

For an Enterprise Architect, understanding **agent-to-system integration** is critical.

---

# 25. Guardrails

Generative AI introduces risks that traditional applications don't necessarily have.

Examples:

* Prompt injection
* Sensitive information disclosure
* Toxic content
* Unauthorized actions
* Hallucinations
* Inappropriate responses

Therefore:

```text
User
 ↓
Application
 ↓
Guardrails
 ↓
Foundation Model
 ↓
Guardrails
 ↓
Response
```

Guardrails are an important part of enterprise GenAI architecture.

---

# 26. Amazon Q

Amazon Q represents another part of the AWS GenAI landscape.

The basic distinction is:

**Bedrock:**

> Build your own generative-AI applications.

**Amazon Q:**

> Use an enterprise-oriented AI assistant experience.

For example, organizations can use Q-oriented capabilities to help users interact with organizational information and improve developer productivity.

---

# 27. AI Agents vs Traditional Automation

This distinction is important.

Traditional automation:

```text
IF condition
THEN action
```

AI agent:

```text
Goal
 ↓
Understand
 ↓
Plan
 ↓
Choose tools
 ↓
Execute
 ↓
Observe
 ↓
Adjust
```

The agent introduces a degree of autonomy.

That creates new architecture concerns:

* Permissions
* Identity
* Tool access
* Auditability
* Human approval
* Failure handling
* Cost controls

---

# 28. AI + AWS Lambda

Lambda is frequently used as an integration mechanism.

Example:

```text
Bedrock Agent
      |
      ▼
    Lambda
      |
      ▼
Enterprise API
      |
      ▼
Database
```

This is a powerful enterprise pattern because the model doesn't need direct access to your databases.

Instead:

```text
AI
 ↓
Controlled Tool
 ↓
Business API
 ↓
Data
```

This provides a much better security boundary.

---

# 29. AI + API Gateway

Another common pattern:

```text
Client
  ↓
API Gateway
  ↓
Lambda / ECS
  ↓
Bedrock
  ↓
Foundation Model
```

API Gateway can provide:

* Authentication
* Authorization
* Throttling
* API management
* Monitoring

This is preferable to exposing AI infrastructure directly to consumers.

---

# 30. AI + Data Lake

Enterprise AI depends heavily on data.

A common AWS architecture is:

```text
Enterprise Sources
       |
       ▼
      S3
       |
       ▼
 AWS Glue / Lake Formation
       |
       ▼
 Data Lake
       |
       ├─────────────┐
       ▼             ▼
   SageMaker      Bedrock
       |             |
       ▼             ▼
    ML Models       GenAI
```

This is where your **data architecture and enterprise architecture skills** become extremely valuable.

---

# 31. AI + Databases

AI applications may need access to:

* Relational databases
* NoSQL databases
* Data warehouses
* Data lakes
* Vector stores

A modern AI application might look like:

```text
User
 ↓
AI Application
 ↓
Bedrock
 ↓
RAG
 ├── S3
 ├── OpenSearch
 ├── Aurora
 └── Other enterprise data
```

---

# 32. Vector Databases

Vector databases are important because traditional keyword searches aren't sufficient for many AI applications.

Traditional search:

```text
"cloud security"
```

looks primarily for matching words.

Semantic search asks:

> "Which documents have concepts related to securing cloud infrastructure?"

Vectors allow semantic similarity to be calculated.

AWS architectures can use vector-search capabilities through services such as **Amazon OpenSearch Service** and supported database/vector-store patterns.

---

# 33. AI Infrastructure

At the bottom of the stack, AWS provides infrastructure.

### Compute

* EC2
* ECS
* EKS
* Lambda
* Specialized ML infrastructure

### Storage

* S3
* EBS
* EFS

### Databases

* Aurora
* RDS
* DynamoDB
* OpenSearch

### Networking

* VPC
* PrivateLink
* Load Balancers
* Transit Gateway

### Security

* IAM
* KMS
* Secrets Manager
* CloudTrail

This gives you the infrastructure required to build AI systems.

---

# 34. GPUs and AI Infrastructure

Training large neural networks requires substantial compute.

AI workloads may use GPU-based infrastructure.

The architecture becomes:

```text
Training Data
     ↓
     S3
     ↓
SageMaker / Compute
     ↓
GPU Infrastructure
     ↓
Model
```

Inference can then be performed through managed endpoints or other deployment patterns.

---

# 35. MLOps

Once you build an ML model, you need to operate it.

This is analogous to DevOps, but for machine learning.

```text
Development
     ↓
Training
     ↓
Testing
     ↓
Model Registry
     ↓
Deployment
     ↓
Monitoring
     ↓
Retraining
```

Key concepts:

* Model versioning
* Data versioning
* Model testing
* Continuous training
* Continuous deployment
* Model monitoring
* Drift detection

---

# 36. LLMOps

Generative AI introduces another operational discipline:

**LLMOps**

It includes:

* Prompt management
* Model selection
* Model evaluation
* Token monitoring
* RAG evaluation
* Retrieval quality
* Hallucination monitoring
* Agent monitoring
* Guardrails
* Cost management

So you can think of:

```text
DevOps
   ↓
MLOps
   ↓
LLMOps
```

as increasingly specialized operational disciplines.

---

# 37. AI Security Architecture

For enterprise AWS AI, security should be designed into every layer.

```text
                 AI SECURITY
                     │
     ┌───────────────┼────────────────┐
     │               │                │
 Identity          Data             Model
     │               │                │
 IAM               KMS           Guardrails
     │               │                │
     └───────────────┼────────────────┘
                     │
                Monitoring
                     │
                  CloudTrail
```

Important controls include:

* IAM
* Least privilege
* Encryption
* Private networking
* Data classification
* Secrets management
* Logging
* Auditing
* Guardrails
* Human approval
* Agent permissions

---

# 38. Responsible AI

Enterprise AI also needs controls around:

* Bias
* Fairness
* Explainability
* Transparency
* Privacy
* Accountability
* Human oversight

The architecture therefore extends beyond technology.

You need:

```text
AI Technology
     +
Security
     +
Governance
     +
Risk Management
     +
Compliance
```

---

# 39. AI Governance

For an enterprise architect, this is one of the most important areas.

A mature AI governance model should cover:

### Data

Who can use the data?

### Models

Which models are approved?

### Prompts

Which prompts/applications are approved?

### Agents

What actions can an agent perform?

### Users

Who can access AI capabilities?

### Vendors

Which external models can be used?

### Compliance

What regulations and policies apply?

---

# 40. AI FinOps

Generative AI introduces a different cost model.

Traditional application:

```text
CPU + RAM + Storage + Network
```

LLM application:

```text
Model
+
Input tokens
+
Output tokens
+
Retrieval
+
Vector storage
+
Inference
+
Application infrastructure
```

Therefore, architects need to consider:

* Model selection
* Token consumption
* Prompt size
* Response size
* Caching
* Batch processing
* Model routing
* Inference frequency

---

# 41. The AWS AI Decision Tree

One of the most useful things to memorize is this:

### Question 1

**Do I need a specific prebuilt AI capability?**

Consider:

* Rekognition
* Textract
* Transcribe
* Polly
* Translate
* Comprehend

### Question 2

**Do I need to build/train/manage my own ML model?**

Consider:

**SageMaker**

### Question 3

**Do I want to build an application using a foundation model?**

Consider:

**Amazon Bedrock**

### Question 4

**Does the application need enterprise knowledge?**

Consider:

**RAG / Bedrock Knowledge Bases**

### Question 5

**Does the AI need to perform actions?**

Consider:

**Agents + APIs + Lambda**

### Question 6

**Does the organization need an enterprise AI assistant experience?**

Consider:

**Amazon Q**

---

# 42. The Big Picture

You can summarize the entire AWS AI landscape this way:

```text
                         AWS AI
                           │
       ┌───────────────────┼────────────────────┐
       │                   │                    │
       ▼                   ▼                    ▼
   AI SERVICES            ML                 GEN AI
       │                   │                    │
       │                   ▼                    ▼
       │              SageMaker             Bedrock
       │                   │                    │
       │            ┌──────┴──────┐      ┌──────┼──────┐
       │            │             │      │      │      │
       ▼          Training      MLOps    FM     RAG   Agents
       │            │             │      │      │      │
       │            ▼             ▼      └──────┼──────┘
       │          Models       Deployment       │
       │                                         ▼
       ├────────────────────────────────── AI Applications
       │                                         │
       │                                         ▼
       └────────────────────────────── Enterprise Systems
```

---

# 43. What You Should Master as an Enterprise Architect

You **do not need to become a research-level ML scientist** to become strong in AWS AI architecture.

I would prioritize these concepts:

### Level 1 — Understand

* AI
* ML
* Deep learning
* Generative AI
* Foundation models
* LLMs
* Embeddings
* Transformers

### Level 2 — Design

* SageMaker architecture
* Bedrock architecture
* RAG
* Vector search
* AI agents
* AI APIs
* AI data pipelines

### Level 3 — Secure

* IAM
* Encryption
* VPC/private connectivity
* Guardrails
* Data protection
* Agent permissions
* Audit

### Level 4 — Operate

* MLOps
* LLMOps
* Monitoring
* Model evaluation
* Cost management
* Reliability

### Level 5 — Govern

* AI governance
* Responsible AI
* Risk management
* Compliance
* Model lifecycle
* Data governance

---

## The most important mental model

For your AWS AI studies, I recommend remembering this hierarchy:

**AI → ML → Deep Learning → Foundation Models → Generative AI → RAG → AI Agents → Autonomous Enterprise Applications**

And on AWS:

**AWS AI Services → SageMaker → Bedrock → Knowledge Bases/RAG → Agents → Enterprise AI Platform**

The transition from **Bedrock → RAG → Agents → enterprise integration** is particularly important because it moves you from simply understanding AI to being able to **architect production enterprise AI systems**.
