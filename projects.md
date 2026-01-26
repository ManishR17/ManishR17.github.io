---
layout: page
title: "Projects"
permalink: /projects/
---

This page documents **end-to-end systems** I’ve designed and built, with
emphasis on architecture, trade-offs, and production constraints.

---

## <a id="elitecontent"></a> EliteContent – Full-Stack Generative AI Platform

### Problem
Generic LLM applications struggle in production due to hallucinations,
lack of grounding, and limited control over context.

### System Architecture
The platform follows a Retrieval-Augmented Generation (RAG) architecture:

1. User request
2. Vector-based retrieval from domain data
3. Policy-enforced context selection (MCP)
4. LLM inference
5. Evaluation and feedback loop

### Key Design Decisions
- **RAG over fine-tuning** for freshness, auditability, and control
- **MCP-based context control** to enforce bounded, deterministic behavior
- **Evaluation-first design** using automated checks and feedback signals

### Implementation Highlights
- Backend: FastAPI
- Retrieval: ChromaDB
- LLM Access: AWS Bedrock
- Deployment: Docker + Kubernetes
- APIs: Authentication, rate limiting, caching
- Quality: Multi-stage refinement and RLHF-style feedback loops

---

## <a id="cricket"></a> Intelligent Cricket Batting Analysis System

### Problem
Traditional coaching feedback is subjective and delayed, limiting
effective skill correction.

### Approach
- Pose estimation for joint tracking
- Biomechanical feature extraction
- Adaptive feedback logic for real-time correction

### System Flow
1. Video input
2. Pose detection
3. Feature extraction
4. Deviation analysis
5. Real-time coaching feedback

### Key Learnings
- Latency constraints dominate model choice
- Interpretability matters more than raw accuracy
- Feedback timing strongly affects motor learning

---

## <a id="enterprise-genai"></a> Enterprise Generative AI Systems

### Focus
High-level architectural patterns for deploying LLM-based systems in
regulated, enterprise environments.

### Core Principles
- Grounding via retrieval
- Deterministic context selection
- Auditable inference
- Stateless, scalable services

### Architecture Themes
- RAG over domain-specific fine-tuning
- Policy-based controls and guardrails
- Evaluation before broad rollout

(Details are intentionally high-level and non-confidential.)

---

## <a id="applied-ml"></a> Applied Machine Learning Systems (2020–2022)

### Overview
Built and deployed production ML systems for classification and
recommendation use cases.

### Typical Pipeline
- Data ingestion and preprocessing
- Feature engineering
- Model training and evaluation
- FastAPI-based inference services
- Monitoring and stability tracking

### Models Used
- Logistic Regression
- Random Forest / Gradient Boosting
- CNNs for image classification
- NLP models for text classification

### Key Learnings
- Model selection should follow data characteristics
- Evaluation is as important as training
- Production integration is the hardest part of ML

---

## <a id="evaluation"></a> LLM Evaluation & Safety

### Problem
LLM output quality is difficult to measure and control in production.

### Evaluation Strategy
- Automated checks for low-quality outputs
- Preference signals from users
- Human-in-the-loop review
- Continuous feedback loops

### Why This Matters
Evaluation is the primary lever for improving
LLM reliability, alignment, and trust.
