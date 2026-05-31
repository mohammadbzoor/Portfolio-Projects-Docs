<div align="center">

# TechNetwork - AI Pipelines

### Candidate-side resume analysis and recruiter-side semantic matching workflows

This document explains the AI layer I worked on in **TechNetwork**, divided into two main parts:

**AI Resume Analyzer** for developers and **Semantic Recruitment Engine** for companies and recruiters.

<br />

![OpenAI](https://img.shields.io/badge/OpenAI-AI-black)
![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![ATS](https://img.shields.io/badge/ATS-Resume%20Analysis-blue)
![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Database-blue)
![Cohere](https://img.shields.io/badge/Cohere-Reranking-green)
![Vector Search](https://img.shields.io/badge/AI-Semantic%20Search-purple)
![PDF](https://img.shields.io/badge/PDF-Processing-red)
![JSON](https://img.shields.io/badge/API-JSON-green)

<br />

[![Back to TechNetwork Overview](https://img.shields.io/badge/Back%20to-TechNetwork%20Overview-purple?style=for-the-badge)](./README.md)
[![Frontend Docs](https://img.shields.io/badge/View-Frontend%20Docs-blue?style=for-the-badge)](./frontend-development.md)
[![AI Repository](https://img.shields.io/badge/View-AI%20Workflow%20Repository-brightgreen?style=for-the-badge)](https://github.com/mohammadbzoor/n8n-ai-resume-analyzer)

</div>

---

## Overview

The AI layer in **TechNetwork** was designed to improve both sides of the recruitment process:

| Side           | Purpose                                                                                                                       |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Candidate Side | Help developers analyze and improve their resumes through ATS scoring and structured AI feedback                              |
| Recruiter Side | Help companies discover relevant candidates using semantic search, vector embeddings, reranking, and natural language queries |

My contribution focused on designing and supporting AI workflows using **n8n**, **OpenAI**, **webhooks**, structured JSON outputs, and vector-based recruitment concepts.

---

# 1. Candidate-Side AI Resume Analyzer

## Purpose

The **AI Resume Analyzer** helps developers upload their CVs and receive structured resume feedback.

It focuses on:

* ATS compatibility analysis
* Resume quality evaluation
* Strengths and weaknesses detection
* Missing keyword identification
* Actionable improvement recommendations
* Structured JSON output for platform integration

---

## ATS Resume Analysis Architecture

<div align="center">

<img width="1390" height="431" alt="ATS Resume Analysis Architecture" src="https://github.com/user-attachments/assets/a93113da-f002-490e-ae8d-eedee18a17c0" />

</div>

This architecture represents the candidate-side AI ecosystem responsible for resume upload processing, PDF extraction, ATS scoring, resume optimization, structured AI evaluation, and intelligent CV assistance workflows.

---

## Candidate-Side Features

| Feature           | Description                                                     |
| ----------------- | --------------------------------------------------------------- |
| ATS Scoring       | Generates a resume score based on compatibility and structure   |
| Resume Evaluation | Detects strengths, weaknesses, and improvement areas            |
| Missing Keywords  | Identifies important missing technical or professional keywords |
| PDF Processing    | Validates and extracts resume text from uploaded PDF files      |
| Resume Cleaning   | Cleans and normalizes extracted resume text                     |
| CV Hashing        | Generates a hash to support resume tracking and processing      |
| Structured JSON   | Returns AI output in a backend-ready JSON format                |
| CV Assistant      | Supports resume-focused Q&A and improvement suggestions         |

---

## Candidate-Side Workflow

```text
Candidate uploads CV
        ↓
PDF validation
        ↓
PDF text extraction
        ↓
Resume cleaning and normalization
        ↓
CV hash generation
        ↓
Payload preparation
        ↓
OpenAI-based resume analysis
        ↓
ATS score and structured feedback
        ↓
JSON response returned to the platform
```

---

## ATS Analysis Example

<div align="center">

<img width="763" height="681" alt="ATS Analysis Example" src="https://github.com/user-attachments/assets/c572895b-a1d3-477d-ad31-5c64ed88a9ed" />

</div>

The ATS engine generates:

* ATS score
* ATS level
* Resume strengths
* Resume weaknesses
* Missing keywords
* Actionable recommendations
* Structured resume summary

---

## Example JSON Output

```json
{
  "success": true,
  "userId": 139,
  "chatId": 35,
  "cvId": 35,
  "atsScore": 78,
  "atsLevel": "Good",
  "status": "Good",
  "summary": "Backend Software Developer with 2 years of experience in building scalable server-side systems and integrating AI solutions.",
  "strengths": [
    "Strong technical skills in multiple programming languages and frameworks",
    "Experience with AI integration and scalable system development",
    "Active involvement in technical content creation and leadership roles"
  ],
  "weaknesses": [
    "Lack of measurable achievements in professional experience",
    "Projects lack specific outcomes or metrics",
    "Formatting could be improved for better readability"
  ],
  "recommendations": [
    "Add measurable achievements to the professional experience section, such as performance improvements, efficiency gains, or completed project impact.",
    "Include specific outcomes for projects to demonstrate business or technical value.",
    "Improve formatting consistency by using clear section headings, aligned dates, and concise bullet points."
  ],
  "isAnalyzed": true
}
```

---

# 2. Recruiter-Side Semantic Recruitment Engine

## Purpose

The **Semantic Recruitment Engine** helps companies and recruiters search for candidates using meaning and technical context instead of relying only on exact keyword matching.

It focuses on:

* Candidate preprocessing
* Vector embeddings generation
* Candidate vector indexing
* Pinecone vector storage
* Semantic candidate retrieval
* Cohere reranking
* AI-assisted candidate matching
* Structured JSON response generation

---

## AI Recruitment Engine Architecture

<div align="center">

<img width="747" height="658" alt="AI Recruitment Engine Architecture" src="https://github.com/user-attachments/assets/561c309c-995e-479f-a118-3f8581fd0650" />

</div>

This architecture represents the recruiter-side AI recruitment engine responsible for candidate preprocessing, vector indexing, semantic retrieval, intelligent reranking, and AI-powered hiring automation.

---

## Recruiter-Side Features

| Feature                 | Description                                                               |
| ----------------------- | ------------------------------------------------------------------------- |
| Candidate Preprocessing | Prepares candidate skills, projects, experience, and portfolio data       |
| OpenAI Embeddings       | Converts candidate data and recruiter queries into vector representations |
| Pinecone Vector Storage | Stores candidate vectors for fast semantic retrieval                      |
| Semantic Search         | Retrieves candidates based on meaning, not exact keywords                 |
| Cohere Reranking        | Improves candidate ranking relevance                                      |
| Natural Language Search | Allows recruiters to search using normal hiring language                  |
| Candidate Matching      | Returns candidates based on technical context and profile relevance       |
| Structured JSON         | Returns clean results that can be consumed by the platform                |

---

## Recruitment Workflow

```text
Recruiter Request
        ↓
Candidate Preprocessing
        ↓
Vector Embeddings Generation
        ↓
Pinecone Vector Storage
        ↓
Semantic Candidate Retrieval
        ↓
Cohere Reranking
        ↓
AI Recruitment Assistant
        ↓
Structured JSON Response
```

---

## Candidate Indexing Flow

```text
Candidate profile created or updated
        ↓
Collect skills, projects, experiences, and portfolio data
        ↓
Normalize candidate text
        ↓
Split and prepare profile content
        ↓
Generate vector embeddings
        ↓
Store candidate vectors in Pinecone
```

---

## Semantic Search Flow

```text
Company submits a natural language search query
        ↓
Normalize recruiter request
        ↓
Generate query embeddings
        ↓
Search candidate vector database
        ↓
Retrieve semantically relevant candidates
        ↓
Rerank candidate results
        ↓
Return structured candidate matches
```

---

## Example Recruiter Query

```text
Need a React developer with experience in AI automation, dashboards, and API integration
```

Instead of searching only for exact keywords, the workflow understands the meaning behind the query and returns candidates whose profiles match the technical context.

---

## Example JSON Output

```json
{
  "success": true,
  "query": "Need a React developer with experience in AI automation and dashboards",
  "matches": [
    {
      "candidateId": 21,
      "name": "Candidate Name",
      "matchScore": 0.91,
      "matchedSkills": ["React.js", "API Integration", "AI Automation"],
      "reason": "Candidate has strong React experience, dashboard projects, and AI workflow integration exposure."
    }
  ]
}
```

---

# Technologies Used

## Automation

* n8n
* Webhooks
* Workflow orchestration
* API routing

## AI and Search

* OpenAI Chat Models
* OpenAI Embeddings
* Pinecone Vector Database
* Cohere Reranking
* Semantic Search
* Vector Retrieval

## Processing

* PDF extraction
* JavaScript preprocessing
* Resume normalization
* Candidate profile normalization
* JSON response formatting

## Platform Integration

* Webhook-based APIs
* Structured workflow pipelines
* Backend integration
* Frontend-ready structured responses

---

# My Contribution

My contribution in the AI layer focused on building and supporting workflow logic that connects the recruitment platform with AI-powered processing.

| Area                 | Contribution                                                            |
| -------------------- | ----------------------------------------------------------------------- |
| n8n Workflows        | Designed and supported candidate-side and recruiter-side workflow logic |
| OpenAI Integration   | Connected resume and recruitment data with AI models                    |
| ATS Analysis         | Supported resume scoring and structured feedback generation             |
| PDF Processing       | Supported resume extraction, cleaning, and preprocessing                |
| Semantic Search      | Worked with candidate matching concepts based on embeddings and context |
| Pinecone Integration | Supported vector-based candidate search and indexing concepts           |
| JSON Outputs         | Structured AI responses for backend storage and frontend display        |
| Platform Integration | Supported webhook communication between the platform and AI workflows   |

---

# Development Highlights

* Built candidate-side AI workflows for resume analysis and ATS scoring
* Supported recruiter-side semantic search and candidate matching logic
* Used n8n as an orchestration layer for AI workflow automation
* Connected OpenAI models with resume and candidate data
* Worked with structured JSON outputs for platform integration
* Supported vector search concepts for intelligent recruitment matching
* Helped build an AI layer that delivers real business value inside TechNetwork

---

# Related Documentation

* [Back to TechNetwork Overview](./README.md)
* [View Frontend Documentation](./frontend-development.md)
* [View Public AI Workflow Repository](https://github.com/mohammadbzoor/n8n-ai-resume-analyzer)
