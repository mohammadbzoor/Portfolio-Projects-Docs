<div align="center">

# TechNetwork: AI Pipelines

### Resume analysis for developers and semantic candidate matching for recruiters

![OpenAI](https://img.shields.io/badge/OpenAI-AI-black)
![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Database-blue)
![Cohere](https://img.shields.io/badge/Cohere-Reranking-green)

[![Back to Overview](https://img.shields.io/badge/Back%20to-Overview-purple?style=for-the-badge)](./README.md)
[![Frontend Docs](https://img.shields.io/badge/View-Frontend%20Docs-blue?style=for-the-badge)](./frontend-development.md)
[![n8n Workflows](https://img.shields.io/badge/View-n8n%20Workflows-brightgreen?style=for-the-badge)](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks)

</div>

---

## Overview

The AI layer of TechNetwork has two parts, one for each side of the platform. Both are built as n8n workflows triggered by webhooks from the Laravel backend, so heavy tasks like PDF parsing and LLM calls do not block the main server.

| Side | Purpose |
|---|---|
| Developers | Upload a CV and receive an ATS score with structured feedback |
| Recruiters | Search candidates in natural language and get ranked matches |

---

# 1. Resume Analyzer (Developer Side)

Developers upload a CV as a PDF. The workflow extracts the text, analyzes it with OpenAI, and returns a structured JSON result that the platform stores and displays.

<div align="center">

<img width="1390" height="431" alt="ATS Resume Analysis Architecture" src="https://github.com/user-attachments/assets/a93113da-f002-490e-ae8d-eedee18a17c0" />

</div>

## What It Produces

- ATS score and level
- Strengths and weaknesses
- Missing keywords
- Actionable improvement recommendations
- A short structured summary of the CV

## Workflow

```text
Developer uploads CV (PDF)
        ↓
PDF validation
        ↓
Text extraction
        ↓
Cleaning and normalization
        ↓
CV hash generation
        ↓
Payload preparation
        ↓
OpenAI analysis
        ↓
ATS score and structured feedback
        ↓
JSON response returned to the platform
```

## Analysis Example

<div align="center">

<img width="763" height="681" alt="ATS Analysis Example" src="https://github.com/user-attachments/assets/c572895b-a1d3-477d-ad31-5c64ed88a9ed" />

</div>

## Response Shape

```json
{
  "success": true,
  "userId": 1,
  "cvId": 1,
  "atsScore": 78,
  "atsLevel": "Good",
  "summary": "Backend developer with 2 years of experience in server-side systems and AI integration.",
  "strengths": [
    "Strong technical skills across multiple languages and frameworks",
    "Experience with AI integration"
  ],
  "weaknesses": [
    "No measurable achievements in professional experience",
    "Projects lack specific outcomes or metrics"
  ],
  "recommendations": [
    "Add measurable achievements such as performance improvements or project impact.",
    "Include specific outcomes for each project."
  ],
  "isAnalyzed": true
}
```

---

# 2. Semantic Recruitment Engine (Recruiter Side)

Recruiters describe the candidate they need in normal language. The engine finds candidates by meaning rather than exact keywords, reranks them, and returns structured matches.

<div align="center">

<img width="747" height="658" alt="AI Recruitment Engine Architecture" src="https://github.com/user-attachments/assets/561c309c-995e-479f-a118-3f8581fd0650" />

</div>

## Components

| Component | Role |
|---|---|
| Candidate preprocessing | Prepares skills, projects, experience, and portfolio data |
| OpenAI Embeddings | Converts candidate data and recruiter queries into vectors |
| Pinecone | Stores candidate vectors for fast semantic retrieval |
| Cohere Reranking | Improves the relevance order of the retrieved candidates |
| OpenAI chat model | Generates the match explanation for each candidate |

## Candidate Indexing Flow

Runs when a candidate profile is created or updated.

```text
Profile created or updated
        ↓
Collect skills, projects, experience, and portfolio data
        ↓
Normalize text
        ↓
Split into chunks (Recursive Character Text Splitter)
        ↓
Generate embeddings
        ↓
Store vectors in Pinecone
```

## Semantic Search Flow

Runs when a company submits a search query.

```text
Natural language query
        ↓
Normalize request
        ↓
Generate query embedding
        ↓
Search Pinecone
        ↓
Rerank results with Cohere
        ↓
Return structured matches
```

## Example Query

```text
Need a React developer with experience in AI automation, dashboards, and API integration
```

The query is matched against candidate profiles by meaning, so a candidate who built dashboards and AI workflows can match even if the exact words differ.

## Response Shape (illustrative)

```json
{
  "success": true,
  "query": "Need a React developer with experience in AI automation and dashboards",
  "matches": [
    {
      "candidateId": 1,
      "matchScore": 0.91,
      "matchedSkills": ["React.js", "API Integration", "AI Automation"],
      "reason": "Strong React experience, dashboard projects, and AI workflow integration."
    }
  ]
}
```

---

# Technologies

| Area | Tools |
|---|---|
| Orchestration | n8n, Webhooks |
| AI | OpenAI chat models, OpenAI Embeddings |
| Search | Pinecone, Cohere Reranking |
| Processing | PDF extraction, JavaScript preprocessing, JSON formatting |

---

# My Contribution

| Area | What I did |
|---|---|
| n8n workflows | Built the resume analysis and recruitment workflows |
| OpenAI integration | Connected CV and candidate data to OpenAI for analysis and matching |
| ATS analysis | Built CV scoring and structured feedback generation |
| PDF processing | Built extraction, cleaning, and preprocessing of uploaded CVs |
| Vector search | Built candidate indexing and semantic search with Pinecone and Cohere |
| Platform integration | Connected the workflows to the Laravel backend through webhooks and returned frontend-ready JSON |

---

# Related Documentation

- [Back to Overview](./README.md)
- [Frontend Documentation](./frontend-development.md)
- [n8n Workflow Files](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks)
