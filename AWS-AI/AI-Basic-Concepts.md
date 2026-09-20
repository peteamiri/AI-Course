# AI Concepts and Definitions — Comprehensive Reference

Below is a structured **AI terminology reference** that progresses from basic concepts to advanced **Machine Learning, Deep Learning, Generative AI, LLMs, RAG, AI Agents, MLOps, and AI architecture**.

---

# 1. Artificial Intelligence Fundamentals

| Concept                                   | Definition                                                                                                                                                                                                   |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Artificial Intelligence (AI)**          | The field of computing concerned with creating systems capable of performing tasks associated with human intelligence, such as perception, reasoning, learning, prediction, generation, and decision-making. |
| **Narrow AI**                             | AI designed to perform a specific task or limited set of tasks. Almost all deployed AI today falls into this category.                                                                                       |
| **Artificial General Intelligence (AGI)** | A hypothetical AI system capable of performing a broad range of intellectual tasks at approximately human-level generality.                                                                                  |
| **Superintelligence**                     | A hypothetical AI whose general intellectual capabilities substantially exceed those of humans.                                                                                                              |
| **AI system**                             | A complete system incorporating models, data, software, infrastructure, interfaces, and potentially automated decision-making or actions.                                                                    |
| **AI model**                              | A computational representation that has learned patterns or relationships from data and can use them to produce predictions, classifications, decisions, or generated content.                               |
| **AI application**                        | A software application that uses one or more AI models to provide a business or user-facing capability.                                                                                                      |
| **Inference**                             | The process of using a trained AI model to generate a prediction, classification, response, or other output from new input.                                                                                  |
| **Training**                              | The process of adjusting a model's parameters using data so that it learns useful patterns.                                                                                                                  |
| **AI pipeline**                           | A sequence of data, processing, model, evaluation, deployment, and monitoring steps used to build or operate an AI system.                                                                                   |

---

# 2. Artificial Intelligence Paradigms

### Rule-Based AI

AI based primarily on explicitly programmed rules.

```text
IF condition
THEN action
```

Example:

```text
IF account_balance < 0
THEN flag_account()
```

### Symbolic AI

AI based on explicit representations of knowledge, logic, rules, and symbolic reasoning.

### Statistical AI

AI approaches that use statistical methods to infer patterns from data.

### Data-Driven AI

AI systems whose behavior is learned primarily from data rather than manually encoded rules.

### Hybrid AI

Combines multiple approaches, such as:

```text
Neural Network
      +
Rules
      +
Knowledge Graph
      +
Search
```

---

# 3. Machine Learning

## Machine Learning (ML)

A subset of AI in which algorithms learn patterns from data and use those patterns to make predictions or decisions.

```text
Data
 ↓
Learning Algorithm
 ↓
Model
 ↓
New Data
 ↓
Prediction
```

## Dataset

A collection of data used to train, validate, or test an AI model.

## Feature

An input variable used by an ML model.

Example:

```text
Age
Income
Location
Credit history
```

## Label

The known target/output associated with a training example.

Example:

```text
Transaction → Fraud
```

"Fraud" is the label.

## Training Dataset

Data used to train the model.

## Validation Dataset

Data used during development to evaluate model performance and tune the model.

## Test Dataset

Previously unseen data used to estimate final model performance.

---

# 4. Types of Machine Learning

## Supervised Learning

Learning from examples where the desired output is known.

```text
Input + Label
     ↓
 Training
     ↓
  Model
```

Examples:

* Fraud classification
* Spam detection
* House-price prediction

---

## Unsupervised Learning

Learning patterns from data without predefined labels.

Examples:

* Customer segmentation
* Clustering
* Anomaly discovery

---

## Semi-Supervised Learning

Uses a combination of labeled and unlabeled data.

Useful when labeling data is expensive.

---

## Self-Supervised Learning

The system generates learning signals from the data itself.

This approach is fundamental to many modern foundation models.

---

## Reinforcement Learning

An agent learns by interacting with an environment and receiving rewards or penalties.

```text
Agent
 ↓ Action
Environment
 ↓
Reward
 ↓
Agent learns
```

---

# 5. Common Machine-Learning Tasks

## Classification

Predicting a category.

Example:

```text
Email → Spam
```

## Binary Classification

Classification with two possible outcomes.

```text
Fraud / Not Fraud
```

## Multiclass Classification

Classification among multiple categories.

```text
Low / Medium / High
```

## Regression

Predicting a numerical value.

Example:

```text
House characteristics → $650,000
```

## Clustering

Grouping similar data points.

## Anomaly Detection

Identifying observations that differ significantly from expected patterns.

## Recommendation

Predicting items or actions likely to be relevant to a user.

## Forecasting

Predicting future values based on historical data.

---

# 6. Model Training Concepts

## Algorithm

A mathematical/computational procedure used to learn from data.

## Model Parameters

Values learned by the model during training.

## Hyperparameters

Configuration values selected before or during training rather than learned directly as model parameters.

Examples:

* Learning rate
* Batch size
* Number of epochs

## Learning Rate

Controls how aggressively model parameters are updated during training.

## Epoch

One complete pass through the training dataset.

## Batch

A subset of training examples processed together.

## Batch Size

Number of examples processed in one training iteration.

## Iteration

One model-update step, generally associated with processing one batch.

---

# 7. Model Performance

## Accuracy

Percentage of predictions that are correct.

## Precision

Of the items predicted as positive, the percentage that actually are positive.

## Recall

Of the actual positive items, the percentage correctly identified.

## F1 Score

Harmonic mean of precision and recall.

## Confusion Matrix

A table showing:

* True positives
* True negatives
* False positives
* False negatives

## ROC Curve

A curve used to evaluate binary classification performance across different thresholds.

## AUC

Area Under the ROC Curve.

---

# 8. Overfitting and Underfitting

## Overfitting

The model learns the training data too closely and performs poorly on new data.

```text
Training performance: Excellent
New-data performance: Poor
```

## Underfitting

The model is too simple to capture important patterns.

```text
Training performance: Poor
New-data performance: Poor
```

## Generalization

The ability of a model to perform effectively on previously unseen data.

---

# 9. Bias and Variance

## Bias

Error resulting from assumptions that are too simplistic or restrictive.

## Variance

Sensitivity of a model to differences in training data.

### Bias-Variance Tradeoff

A model should balance:

```text
Too simple → High bias

Too complex → High variance
```

---

# 10. Feature Engineering

## Feature Engineering

Creating, transforming, or selecting input variables to improve model performance.

Example:

Raw data:

```text
Date = 2026-09-11
```

Potential features:

```text
Day of week
Month
Weekend indicator
```

## Feature Selection

Selecting the most useful features.

## Feature Store

A system for storing, managing, and serving ML features consistently.

---

# 11. Deep Learning

## Deep Learning

A subset of machine learning that uses multi-layer neural networks to learn complex representations from data.

```text
Machine Learning
       ↓
   Deep Learning
       ↓
Neural Networks
```

## Neural Network

A computational model consisting of interconnected layers of mathematical units.

## Neuron

A computational unit that receives inputs, applies weights and an activation function, and produces an output.

## Layer

A group of neurons operating at a particular stage of a neural network.

## Activation Function

A function that introduces nonlinear behavior into a neural network.

Examples:

* ReLU
* Sigmoid
* Tanh
* Softmax

---

# 12. Neural Network Architectures

## CNN — Convolutional Neural Network

Neural-network architecture particularly effective for image and spatial data.

## RNN — Recurrent Neural Network

Architecture designed to process sequential data.

## LSTM

Long Short-Term Memory network designed to handle longer-term dependencies in sequences.

## Transformer

Neural-network architecture based heavily on attention mechanisms and central to modern LLMs and many foundation models.

---

# 13. Attention and Transformers

## Attention

Mechanism that allows a model to determine which parts of an input are most relevant when processing another part of the input.

## Self-Attention

Attention where elements of a sequence attend to other elements within the same sequence.

## Multi-Head Attention

Uses multiple attention mechanisms operating in parallel to capture different relationships.

## Transformer

Architecture built around attention mechanisms and feed-forward neural-network components.

Transformers are fundamental to modern:

* LLMs
* Translation models
* Multimodal models
* Generative AI

---

# 14. Natural Language Processing

## NLP — Natural Language Processing

AI technology for processing and understanding human language.

## Token

A unit of text processed by a language model.

A token might correspond to:

* A word
* Part of a word
* Punctuation
* Other text elements

## Tokenization

Converting text into tokens.

```text
"Hello world"
      ↓
Tokens
```

## Named Entity Recognition

Identifying entities such as:

* People
* Organizations
* Locations
* Dates
* Products

## Sentiment Analysis

Determining sentiment expressed in text.

## Text Classification

Assigning text to predefined categories.

---

# 15. Generative AI

## Generative AI

AI capable of generating new content based on learned patterns and user-provided inputs.

It can generate:

* Text
* Code
* Images
* Audio
* Video
* Structured data

---

# 16. Foundation Models

## Foundation Model

A broadly trained model that can serve as a foundation for many downstream applications.

Instead of:

```text
One model → One task
```

you can have:

```text
Foundation Model
       ↓
 ┌─────┼──────┐
 ↓     ↓      ↓
Chat  Code  Summarization
```

---

# 17. Large Language Models

## LLM

A Large Language Model is a neural model trained on large amounts of language data to perform language-related tasks.

Applications include:

* Question answering
* Summarization
* Code generation
* Translation
* Classification
* Content generation

## Context Window

The amount of information a model can consider within a particular interaction.

## Context

Information supplied to a model to help it generate an appropriate response.

## Prompt

Instructions and information supplied to a generative AI model.

---

# 18. Prompt Engineering

## Prompt Engineering

The practice of designing effective prompts to obtain reliable and useful model outputs.

## Zero-Shot Prompting

Asking the model to perform a task without providing examples.

## Few-Shot Prompting

Providing examples demonstrating the desired behavior.

## System Prompt

High-level instructions establishing the model's behavior and constraints.

## User Prompt

The specific instruction or question supplied by the user.

## Prompt Template

A reusable prompt structure containing variable fields.

---

# 19. Model Adaptation

## Fine-Tuning

Additional training of an existing model using task- or domain-specific data.

```text
Foundation Model
       ↓
Domain Data
       ↓
Fine-Tuning
       ↓
Adapted Model
```

## Instruction Tuning

Training a model to better follow instructions.

## Parameter-Efficient Fine-Tuning

Techniques that adapt a model without updating all of its parameters.

## Transfer Learning

Using knowledge learned for one task/domain to improve another task/domain.

---

# 20. Embeddings

## Embedding

A numerical vector representation of data that captures semantic or other meaningful relationships.

Example:

```text
"Cloud architecture"
        ↓
[0.12, -0.44, 0.83, ...]
```

## Vector

An ordered numerical representation.

## Vector Similarity

A measure of how similar two vectors are.

## Cosine Similarity

A common method for measuring similarity between vectors based on their angular relationship.

---

# 21. RAG

## RAG — Retrieval-Augmented Generation

An architecture that retrieves relevant external information and provides it to a generative model as context.

```text
Question
   ↓
Retrieval
   ↓
Relevant Documents
   ↓
Context
   ↓
LLM
   ↓
Answer
```

## Retriever

Component that searches for relevant information.

## Chunk

A smaller segment of a document used for retrieval.

## Chunking

Breaking large documents into smaller pieces.

## Vector Database

Database optimized for storing and searching vector representations.

## Semantic Search

Search based on meaning rather than exact keyword matching.

---

# 22. Hallucination

## AI Hallucination

When a generative AI model produces information that appears plausible but is incorrect, unsupported, or fabricated.

This is a major enterprise GenAI concern.

Mitigation techniques include:

* RAG
* Grounding
* Structured output
* Validation
* Guardrails
* Human review

---

# 23. Grounding

## Grounding

Constraining or supporting an AI response using trusted external information.

For example:

```text
LLM
 +
Company Knowledge Base
 =
Grounded Answer
```

RAG is one common grounding technique.

---

# 24. Multimodal AI

## Multimodal Model

A model capable of processing or generating multiple types of information.

Examples:

```text
Text
Image
Audio
Video
```

A multimodal model might receive:

```text
Image + Question
```

and produce:

```text
Textual explanation
```

---

# 25. AI Agents

## AI Agent

An AI system capable of pursuing a goal by reasoning about tasks, using tools, obtaining information, and potentially taking actions.

```text
Goal
 ↓
Reason
 ↓
Plan
 ↓
Use Tool
 ↓
Observe Result
 ↓
Continue
```

## Tool Calling

Allowing an AI model/agent to invoke an external function, API, database query, or other capability.

## Function Calling

A structured mechanism allowing a model to request execution of a predefined function.

## Agentic Workflow

A workflow in which an AI system dynamically determines some of the steps required to accomplish a goal.

## Agent Memory

Information retained or retrieved to provide continuity across interactions or tasks.

---

# 26. AI Autonomy

## Human-in-the-Loop

Humans review or approve AI decisions/actions.

```text
AI → Recommendation → Human → Action
```

## Human-on-the-Loop

AI operates more autonomously while humans monitor the system.

## Human-out-of-the-Loop

The system operates without human intervention for the relevant decision/action.

The level of autonomy should increase only when the risk is appropriately controlled.

---

# 27. AI Safety

## AI Safety

The discipline of designing AI systems to minimize harmful, unreliable, or unintended behavior.

## Guardrail

A control that restricts inappropriate model inputs, outputs, or actions.

## Content Filtering

Detecting and blocking inappropriate or prohibited content.

## Prompt Injection

An attack in which malicious instructions attempt to manipulate an AI system into violating its intended behavior.

## Jailbreaking

Attempts to bypass model safety or behavioral restrictions.

---

# 28. AI Security

## AI Security

Protecting AI models, data, applications, infrastructure, and interfaces against attacks and unauthorized use.

Important concerns include:

* Data leakage
* Prompt injection
* Model abuse
* Unauthorized access
* Model theft
* Data poisoning
* Excessive agent permissions

---

# 29. Responsible AI

## Responsible AI

Designing and operating AI systems in ways that emphasize safety, fairness, transparency, privacy, accountability, and appropriate human oversight.

## Fairness

Ensuring AI does not produce unjustified or systematically discriminatory outcomes.

## Explainability

The ability to understand factors contributing to a model's output.

## Transparency

Providing information about how an AI system operates, its limitations, and its appropriate use.

## Accountability

Clearly establishing responsibility for AI system decisions and outcomes.

---

# 30. Model Evaluation

## Model Evaluation

Measuring how well a model performs against defined requirements.

For LLMs, evaluation can include:

* Accuracy
* Relevance
* Factuality
* Helpfulness
* Safety
* Groundedness
* Toxicity
* Latency
* Cost

## Benchmark

A standardized dataset or test used to compare model performance.

## Evaluation Dataset

A dataset specifically used to measure model behavior.

---

# 31. MLOps

## MLOps

Practices and technologies for developing, deploying, monitoring, and maintaining machine-learning systems.

Think:

```text
DevOps
   +
Machine Learning
   =
MLOps
```

Key areas:

* Data pipelines
* Training
* Model registry
* Deployment
* Monitoring
* Retraining
* Governance

---

# 32. LLMOps

## LLMOps

Operational practices specifically associated with large language models and Generative AI.

Includes:

* Prompt management
* Model management
* RAG management
* Evaluation
* Token monitoring
* Cost management
* Guardrails
* Monitoring
* Versioning

---

# 33. Model Deployment

## Model Endpoint

An interface through which applications send inputs to a deployed model and receive predictions.

## Real-Time Inference

Prediction generated immediately in response to a request.

## Batch Inference

Processing large quantities of data in batches rather than individually in real time.

## Serverless Inference

Inference infrastructure managed dynamically by the cloud provider.

---

# 34. Model Monitoring

## Model Monitoring

Continuous observation of model behavior and performance.

## Data Drift

Changes in the statistical properties of input data.

## Concept Drift

Changes in the relationship between inputs and the target being predicted.

## Model Drift

Decline or change in model performance over time.

---

# 35. AI Data Concepts

## Data Lake

Large-scale repository capable of storing structured and unstructured data.

## Data Warehouse

System optimized primarily for analytical queries over structured data.

## Data Pipeline

Automated process that moves and transforms data.

## Data Quality

Measures such as:

* Accuracy
* Completeness
* Consistency
* Timeliness
* Validity

## Data Lineage

Tracking where data originated, how it was transformed, and where it is used.

## Data Governance

Policies, processes, roles, and controls for managing data.

---

# 36. Knowledge Graph

## Knowledge Graph

A graph representation of entities and relationships.

Example:

```text
AWS
 |
└── provides
      |
      └── Amazon Bedrock
                |
                └── supports
                       |
                       └── Generative AI
```

Knowledge graphs can complement RAG and LLM systems.

---

# 37. AI Architecture

## AI Architecture

The design of the components, interfaces, data flows, security controls, infrastructure, models, and operational processes that make up an AI system.

A production architecture might contain:

```text
Users
  ↓
Application
  ↓
API
  ↓
AI Orchestration
  ↓
RAG / Agent
  ↓
Foundation Model
  ↓
Enterprise Data
```

with security and monitoring surrounding the entire system.

---

# 38. AI Governance

## AI Governance

The policies, processes, controls, and responsibilities used to manage AI throughout its lifecycle.

Governance covers:

* Approved models
* Data usage
* Security
* Privacy
* Risk
* Compliance
* Model lifecycle
* Human oversight
* Monitoring
* Audit

---

# 39. AI Risk

## AI Risk

Potential negative consequences resulting from AI behavior, deployment, misuse, or failure.

Examples:

* Incorrect decisions
* Bias
* Security vulnerabilities
* Privacy violations
* Hallucinations
* Regulatory violations
* Financial losses
* Operational failures

---

# 40. AI FinOps

## AI FinOps

Managing the cost and economic efficiency of AI workloads.

Generative AI costs can depend heavily on:

```text
Input tokens
+
Output tokens
+
Model selection
+
Inference frequency
+
Retrieval
+
Storage
+
Compute
```

Architectural decisions can therefore have significant financial consequences.

---

# 41. AWS-Specific AI Concepts

For your AWS AI course, these are especially important.

| Concept                       | AWS relevance                                    |
| ----------------------------- | ------------------------------------------------ |
| **Amazon SageMaker**          | ML development, training, deployment, MLOps      |
| **Amazon Bedrock**            | Foundation models and Generative AI applications |
| **Amazon Q**                  | Enterprise-oriented generative AI experiences    |
| **Bedrock Knowledge Bases**   | Managed RAG/knowledge retrieval capabilities     |
| **Bedrock Agents**            | Agentic applications and tool/API interaction    |
| **Amazon Rekognition**        | Computer vision                                  |
| **Amazon Textract**           | Document and text extraction                     |
| **Amazon Transcribe**         | Speech-to-text                                   |
| **Amazon Polly**              | Text-to-speech                                   |
| **Amazon Comprehend**         | NLP capabilities                                 |
| **Amazon Translate**          | Machine translation                              |
| **Amazon Lex**                | Conversational interfaces                        |
| **Amazon OpenSearch Service** | Search and vector-search architectures           |
| **Amazon S3**                 | AI/ML data storage and data lakes                |
| **AWS Glue**                  | Data integration and preparation                 |
| **AWS Lambda**                | AI application and agent tool integration        |
| **Amazon EKS**                | Containerized AI/ML workloads                    |
| **Amazon EC2**                | Custom AI/ML compute                             |

---

# 42. The AI Concept Hierarchy

The most useful way to organize all of these concepts in your mind is:

```text
                         ARTIFICIAL INTELLIGENCE
                                  │
             ┌────────────────────┼────────────────────┐
             │                    │                    │
             ▼                    ▼                    ▼
       Symbolic AI          Machine Learning       AI Perception
                                  │
                    ┌─────────────┼─────────────┐
                    │             │             │
                    ▼             ▼             ▼
               Supervised    Unsupervised   Reinforcement
                    │
                    ▼
              Deep Learning
                    │
                    ▼
              Neural Networks
                    │
                    ▼
               Transformers
                    │
                    ▼
             Foundation Models
                    │
             ┌──────┴──────┐
             ▼             ▼
            LLMs      Multimodal Models
             │
             ▼
        Generative AI
             │
      ┌──────┼────────┐
      ▼      ▼        ▼
   Prompt   RAG     Agents
 Engineering │        │
             │        ▼
             │     Tool Calling
             │        │
             └────┬───┘
                  ▼
          Enterprise AI
                  │
       ┌──────────┼──────────┐
       ▼          ▼          ▼
   Security   Governance   Operations
       │          │          │
       └──────────┼──────────┘
                  ▼
          Production AI
```

## The 20 concepts I would prioritize first

If your goal is to become an **AWS Enterprise AI / Cloud Solution Architect**, concentrate first on these:

1. **Artificial Intelligence**
2. **Machine Learning**
3. **Supervised Learning**
4. **Deep Learning**
5. **Neural Networks**
6. **Transformers**
7. **Foundation Models**
8. **Large Language Models**
9. **Generative AI**
10. **Prompt Engineering**
11. **Embeddings**
12. **Vector Search**
13. **RAG**
14. **Fine-Tuning**
15. **AI Agents**
16. **Tool/Function Calling**
17. **AI Evaluation**
18. **AI Security**
19. **AI Governance**
20. **MLOps / LLMOps**

The key progression to master is:

**AI → ML → Deep Learning → Transformers → Foundation Models → Generative AI → RAG → Agents → Enterprise AI Architecture.**

That progression gives you the conceptual foundation needed to understand **why AWS uses SageMaker for some workloads and Bedrock for others**, and how those services fit into a larger enterprise architecture.
