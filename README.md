# TrustGraph — Enterprise Trust-Aware Retrieval-Augmented Generation Platform

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/Python-3.12+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-Latest-green)
![React](https://img.shields.io/badge/React-19-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue)
![pgvector](https://img.shields.io/badge/pgvector-Vector%20Search-blue)
![Redis](https://img.shields.io/badge/Redis-7-red)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED)
![LLM](https://img.shields.io/badge/RAG-Trust%20Aware-purple)

### Explainable Retrieval-Augmented Generation with Evidence Verification & Trust Scoring

**Retrieve • Verify • Explain • Score • Trust**

---

</div>

# Table of Contents

- Overview
- Problem Statement
- Solution
- Core Principles
- Key Features
- System Architecture
- Multi-Agent Architecture
- RAG Pipeline
- Retrieval Engine
- Claim Extraction
- Verification Engine
- Trust Scoring
- Evidence Graph
- AI Components
- Technology Stack
- Repository Structure
- API
- Security
- Installation
- Docker
- Monitoring
- Performance
- Roadmap
- License

---

# Overview

TrustGraph is an enterprise-grade Trust-Aware Retrieval-Augmented Generation (RAG) platform designed to produce explainable, evidence-backed AI responses instead of relying solely on Large Language Models.

Unlike traditional RAG systems that retrieve documents and generate answers directly, TrustGraph verifies every factual claim before presenting it to the user.

The platform combines:

- Hybrid Retrieval
- Claim Extraction
- Deterministic Verification
- Rules Engine
- Knowledge Graph Validation
- LLM Verification
- Trust Scoring
- Explainable AI

Every answer includes supporting evidence, verification results, confidence metrics, and an overall trust score.

---

# Problem Statement

Traditional RAG systems suffer from several limitations.

- Hallucinated facts
- Unsupported claims
- Missing citations
- No verification layer
- Opaque confidence scores
- Weak explainability
- Difficult enterprise adoption

Organizations require AI systems that can justify every answer with verifiable evidence.

---

# Solution

TrustGraph introduces a verification-first architecture.

Instead of:

```
Retrieve

↓

LLM

↓

Answer
```

TrustGraph performs:

```
Retrieve

↓

Extract Claims

↓

Verify Claims

↓

Compute Trust

↓

Generate Explainable Answer
```

Every statement is backed by evidence before being shown to users.

---

# Core Design Principles

- Evidence before generation
- Code verifies numbers, not LLMs
- Hybrid retrieval
- Typed contracts
- Explainable trust
- Human-review support
- Enterprise governance
- Modular architecture

---

# Key Features

## Hybrid Retrieval

Combines multiple retrieval methods.

- Dense Embeddings
- BM25
- Keyword Search
- Metadata Filters
- Reciprocal Rank Fusion (RRF)

```
Query

↓

BM25

+

Dense Search

↓

RRF Fusion

↓

Top Evidence
```

---

## Claim Extraction

Generated responses are decomposed into atomic claims.

Example

```
Revenue increased 18%.

Company has 250 employees.

Office opened in Singapore.
```

becomes

```
Claim 1

Revenue increased 18%

Claim 2

250 Employees

Claim 3

Office in Singapore
```

Each claim is independently verified.

---

## Multi-Stage Verification

Claims are routed to specialized verifiers.

Numeric Claims

↓

SQL Verification

Entity Claims

↓

Knowledge Graph

Narrative Claims

↓

LLM Verification

Business Rules

↓

Rules Engine

---

## Deterministic Verification

Numbers are never trusted directly from an LLM.

Instead:

```
Claim

↓

Warehouse Query

↓

Compare

↓

Verified
```

Examples

- Revenue
- Profit
- Sales
- KPI
- Inventory
- Financial Metrics

---

## Knowledge Graph Verification

Entities are verified against enterprise knowledge.

Examples

- Customers
- Products
- Departments
- Vendors
- Locations
- Employees

---

## Narrative Verification

Claims that cannot be verified through deterministic methods are evaluated using LLM reasoning against retrieved evidence.

Examples

- Policies
- Procedures
- Documentation
- Product descriptions

---

## Trust Score

Every answer receives an explainable trust score.

Dimensions include

- Retrieval Quality
- Evidence Coverage
- Claim Verification Rate
- Source Authority
- Freshness
- Conflict Score
- Deterministic Verification Rate

---

# Multi-Agent Architecture

```
User Query

↓

Query Agent

↓

Retriever Agent

↓

Evidence Ranking Agent

↓

Claim Extraction Agent

↓

Verification Router

↓

SQL Verifier

Rules Verifier

Knowledge Graph Verifier

LLM Verifier

↓

Trust Scorer

↓

Response Generator

↓

User
```

---

# Complete RAG Pipeline

```
Question

↓

Hybrid Retrieval

↓

Top Documents

↓

Context Builder

↓

LLM Draft Answer

↓

Claim Extraction

↓

Verification Router

↓

Evidence Matching

↓

Trust Scoring

↓

Explainable Response
```

---

# Retrieval Engine

Supports

- BM25
- Dense Embeddings
- Hybrid Search
- Metadata Filters
- Semantic Search
- Keyword Search
- Reciprocal Rank Fusion

Supported Vector Stores

- pgvector
- Pinecone
- Weaviate
- Qdrant
- Milvus
- Chroma

---

# Evidence Model

Each evidence record contains

- Document ID
- Chunk ID
- Source
- Page Number
- Similarity Score
- Retrieval Method
- Metadata
- Timestamp
- Version

---

# Claim Extraction Engine

Extracts

- Numeric Claims
- Entity Claims
- Narrative Claims
- Dates
- Percentages
- Currency
- Quantities

Each claim includes

- Confidence
- Extraction Method
- Entity Mapping
- Source References

---

# Verification Engine

## SQL Verifier

Checks

- KPIs
- Revenue
- Sales
- Inventory
- Financial Numbers

Against

- Snowflake
- PostgreSQL
- SQL Server

---

## Rules Engine

Checks

- Business Policies
- Thresholds
- Constraints
- Entity Registry
- Compliance Rules

---

## Knowledge Graph Verifier

Verifies

- Customers
- Products
- Employees
- Organizations
- Locations

---

## LLM Verifier

Evaluates

- Narrative Claims
- Documentation
- Policy Statements
- Explanations

using retrieved evidence.

---

# Trust Score

TrustGraph computes explainable trust across seven dimensions.

| Dimension | Description |
|------------|-------------|
| Retrieval Quality | Relevance of retrieved evidence |
| Evidence Coverage | Portion of claims with evidence |
| Claim Verification Rate | Percentage of verified claims |
| Freshness | Recency of sources |
| Conflict Score | Contradictions detected |
| Source Authority | Reliability of sources |
| Deterministic Verification Rate | Claims verified using code |

Overall Trust Score

```
0.91

High Confidence

Verified Claims

Supported Evidence

Low Conflict
```

---

# Explainable Response

Every response contains

```
Answer

↓

Supporting Evidence

↓

Verified Claims

↓

Contradicted Claims

↓

Trust Score

↓

Sources
```

---

# Technology Stack

## Frontend

- React 19
- TypeScript
- Vite
- Tailwind CSS
- React Query
- Zustand
- AG Grid

---

## Backend

- FastAPI
- Python 3.12
- SQLAlchemy
- Pydantic
- AsyncIO

---

## AI

- OpenAI
- Claude
- Gemini
- Local LLMs

---

## Retrieval

- pgvector
- BM25
- Sentence Transformers
- Cross Encoder Reranker

---

## Storage

- PostgreSQL
- Redis
- Object Storage

---

## Infrastructure

- Docker
- Kubernetes
- Prometheus
- Grafana
- OpenTelemetry

---

# Repository Structure

```
trustgraph/

├── frontend/
├── backend/
├── retriever/
├── reranker/
├── claim-extractor/
├── verification/
├── trust-scorer/
├── knowledge-graph/
├── api/
├── monitoring/
├── evaluation/
├── docs/
├── tests/
├── docker/
├── README.md
└── LICENSE
```

---

# High-Level Architecture

```
              User

                │

                ▼

        React Dashboard

                │

                ▼

         FastAPI Gateway

                │

         Query Processing

                │

                ▼

       Hybrid Retrieval

                │

                ▼

       Evidence Ranking

                │

                ▼

      LLM Answer Draft

                │

                ▼

      Claim Extraction

                │

                ▼

     Verification Router

      ┌────────┼─────────┐

      ▼        ▼         ▼

 SQL   Rules   LLM

      ▼

 Trust Scorer

      ▼

 Explainable Response
```

---

# API Endpoints

Authentication

```
POST /api/v1/auth/login
POST /api/v1/auth/logout
```

Query

```
POST /api/v1/query
```

Verification

```
POST /api/v1/verify
GET /api/v1/verification/{id}
```

Trust Score

```
POST /api/v1/trust-score
```

Evidence

```
GET /api/v1/evidence
```

Evaluation

```
POST /api/v1/evaluate
```

---

# Security

- JWT Authentication
- OAuth2
- RBAC
- Audit Logging
- API Rate Limiting
- Encrypted Storage
- TLS
- Row-Level Security

---

# Environment Variables

```env
DATABASE_URL=

REDIS_URL=

JWT_SECRET=

OPENAI_API_KEY=

ANTHROPIC_API_KEY=

GOOGLE_API_KEY=

PGVECTOR_URL=

LOG_LEVEL=

ENABLE_HYBRID_RETRIEVAL=true

ENABLE_VERIFICATION=true

ENABLE_TRUST_SCORE=true
```

---

# Installation

Clone Repository

```bash
git clone https://github.com/your-org/trustgraph.git
```

Backend

```bash
cd backend

pip install -r requirements.txt
```

Frontend

```bash
cd frontend

npm install
```

Run Backend

```bash
uvicorn app.main:app --reload
```

Run Frontend

```bash
npm run dev
```

---

# Docker

```bash
docker compose up --build
```

---

# Monitoring

Integrated with

- Prometheus
- Grafana
- Loki
- OpenTelemetry
- Jaeger

Metrics

- Retrieval Recall
- Precision@K
- MRR
- nDCG
- Trust Score Distribution
- Verification Latency
- Hallucination Rate
- Token Usage
- Cost Per Query

---

# Performance Targets

| Metric | Target |
|---------|---------|
| Retrieval Latency | < 300 ms |
| Verification Latency | < 2 sec |
| End-to-End Response | < 5 sec |
| Recall@10 | > 90% |
| Hallucination Rate | < 2% |
| Availability | 99.9% |

---

# Future Roadmap

## Version 1.1

- Cross-Encoder Reranking
- Multi-Hop Retrieval
- Citation Highlighting
- Source Versioning

## Version 1.2

- Knowledge Graph Expansion
- Multi-Agent Verification
- Semantic Conflict Detection
- Enterprise Connectors

## Version 2.0

- Autonomous Verification Agents
- Continuous Knowledge Validation
- Self-Calibrating Trust Scores
- Multi-Modal RAG
- Enterprise Decision Intelligence
- Federated Knowledge Graph
- AI Evidence Reasoning Engine

---

# License

This project is licensed under the MIT License.

---

# Contributors

TrustGraph is a production-grade Trust-Aware Retrieval-Augmented Generation platform that combines hybrid retrieval, deterministic verification, explainable trust scoring, and evidence-backed AI to deliver reliable enterprise knowledge systems.

---

<div align="center">

# TrustGraph

### **Every Answer Must Earn Trust**

**Retrieve • Verify • Explain • Trust**

</div>
