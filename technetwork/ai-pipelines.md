<div align="center">

# TechNetwork - AI Pipelines

### AI-powered CV analysis and recruitment matching workflows using n8n, OpenAI, and vector search

This document explains my AI pipeline contribution in TechNetwork, including CV analysis, ATS scoring, candidate profile processing, semantic search, and intelligent recruitment matching.

<br />

[![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-LLM%20Integration-412991?style=for-the-badge\&logo=openai\&logoColor=white)](https://openai.com/)
[![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Database-000000?style=for-the-badge)](https://www.pinecone.io/)
[![Semantic Search](https://img.shields.io/badge/Semantic%20Search-Candidate%20Matching-blue?style=for-the-badge)](https://github.com/mohammadbzoor/n8n-ai-resume-analyzer)

</div>

---

## Overview

The AI layer in **TechNetwork** was designed to improve the recruitment process by moving beyond traditional keyword-based hiring.

My contribution focused on AI-powered workflows that support resume analysis, ATS scoring, candidate profile processing, vector indexing, and semantic candidate matching.

These workflows were built using **n8n** as an automation and orchestration layer, connected with AI services such as **OpenAI** and vector search tools such as **Pinecone**.

---

## My AI Pipeline Role

My AI-related responsibilities included:

* Designing AI workflow logic using n8n
* Connecting OpenAI models with the recruitment platform
* Creating webhook-based workflow integrations
* Supporting CV parsing and resume analysis flows
* Generating structured resume feedback
* Supporting ATS scoring logic
* Preparing candidate data for semantic search
* Helping convert developer skills, projects, and experiences into AI-ready searchable data
* Supporting natural language recruitment search flows
* Connecting AI outputs back to the platform in structured formats

---

## AI Workflow Areas

| AI Area                      | Description                                                           |
| ---------------------------- | --------------------------------------------------------------------- |
| CV Analysis                  | Extracts and analyzes resume content                                  |
| ATS Scoring                  | Provides score, strengths, weaknesses, and improvement suggestions    |
| Candidate Profile Processing | Converts developer profile data into structured searchable content    |
| Vector Indexing              | Stores candidate representations as embeddings                        |
| Semantic Search              | Matches candidates based on meaning instead of exact keywords         |
| Recruitment Assistant        | Helps companies search for suitable developers using natural language |
| Webhook Automation           | Connects the web platform with AI workflows through n8n               |

---

## Pipeline 1: CV Analysis Workflow

The CV analysis pipeline is designed to help developers improve their resumes.

### Flow

```text
Developer uploads CV
   ↓
Validate PDF
   ↓
Extract resume text
   ↓
Clean and prepare content
   ↓
Send content to OpenAI model
   ↓
Generate structured analysis
   ↓
Return ATS score, strengths, weaknesses, and suggestions
```

### Output

The workflow returns structured feedback such as:

* ATS score
* Resume strengths
* Resume weaknesses
* Improvement suggestions
* Structured JSON response for backend storage and frontend display

---

## Pipeline 2: Candidate Profile Processing

This workflow prepares developer profile data for intelligent search.

### Flow

```text
Developer profile is created or updated
   ↓
Collect skills, projects, experiences, and portfolio data
   ↓
Normalize text
   ↓
Split and prepare content
   ↓
Generate embeddings using OpenAI
   ↓
Store vectors in Pinecone
```

### Purpose

This allows developer profiles to be searched based on context and meaning rather than only exact keywords.

---

## Pipeline 3: Intelligent Recruitment Matching

This workflow helps companies find suitable candidates using natural language queries.

### Example Query

```text
Need a React developer with experience in AI automation and dashboard systems
```

### Flow

```text
Company submits search query
   ↓
Normalize request through webhook
   ↓
Generate query embeddings
   ↓
Search candidate vector database
   ↓
Rank candidate matches
   ↓
Return relevant candidates to the platform
```

### Result

The system can recommend candidates based on semantic meaning, technical context, and profile relevance.

---

## AI Tech Stack

* n8n
* OpenAI Chat Models
* OpenAI Embeddings
* Webhooks
* Pinecone Vector Database
* Semantic Search
* JSON Processing
* API Integration
* Recruitment Matching Logic

---

## Related Public Repository

The AI workflows and additional documentation are available in this public repository:

[View n8n AI Resume Analyzer Repository](https://github.com/mohammadbzoor/n8n-ai-resume-analyzer)

This repository includes documentation for:

* AI Resume Analyzer
* ATS scoring workflow
* Candidate profile indexing
* Semantic recruitment search
* Recruitment assistant workflow

---

## Development Highlights

* Designed n8n-based AI automation workflows for recruitment use cases
* Connected AI workflows with the platform using webhooks
* Supported AI-powered CV analysis and resume improvement suggestions
* Helped structure ATS score outputs in a format suitable for frontend display
* Worked with embeddings and vector search concepts for candidate matching
* Supported recruiter-side natural language search functionality
* Helped build an AI layer that delivers real business value inside a recruitment platform

---

## What I Learned

Through this AI pipeline work, I improved my skills in:

* Building AI automation workflows using n8n
* Connecting web applications with AI services
* Designing webhook-based integrations
* Structuring AI outputs as JSON
* Working with OpenAI chat models and embeddings
* Understanding semantic search and vector databases
* Building AI-powered recruitment workflows
* Designing systems that connect frontend, backend, and AI automation layers

---

## Related Documentation

* [Back to TechNetwork Overview](./README.md)
* [View Frontend Documentation](./frontend-development.md)
