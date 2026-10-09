<div align="center">

# TechNetwork

### AI-Powered Recruitment Platform for the Tech Industry

Connects developers and companies through structured portfolios, a job board,
AI-based CV analysis, ATS scoring, and semantic candidate search.

![Live Demo](https://img.shields.io/badge/Live%20Demo-TechNetwork-22C55E?style=for-the-badge&logo=googlechrome&logoColor=white)
![React](https://img.shields.io/badge/React.js-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![n8n](https://img.shields.io/badge/n8n-AI%20Workflows-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-LLM-412991?style=for-the-badge&logo=openai&logoColor=white)
![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Search-000000?style=for-the-badge)

[🌐 Live Platform](https://technetworkfront.laravel.cloud/) •
[🤖 n8n Workflows](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks) •
[💼 LinkedIn](https://www.linkedin.com/in/mohammadbzoor)

</div>

---

## Overview

TechNetwork is a graduation project (Computer Science, Al al-Bayt University) built by a team of two.

Developers create profiles with skills, projects, experience, and certificates. Companies publish jobs and search for candidates. The AI layer analyzes uploaded CVs, scores them for ATS compatibility, and lets recruiters search candidates by **meaning** instead of exact keywords.

> **My role:** React frontend, API integration, and the full AI/automation layer (n8n, OpenAI, Pinecone).
> **Teammate's role:** Laravel backend, database, and system architecture.

---

## Screenshots

<!-- Add 4-6 images to a /screenshots folder, then uncomment -->
<!--
| Developer Profile | ATS Score Result |
|---|---|
| ![](screenshots/profile.png) | ![](screenshots/ats.png) |

| Semantic Search | Company Dashboard |
|---|---|
| ![](screenshots/search.png) | ![](screenshots/company.png) |
-->

**Demo access:**
- Developer account: `[email]` / `[password]`
- Company account: `[email]` / `[password]`

> Or watch a short walkthrough: [Demo video](LINK)

---

## Features

| Feature | Description |
|---|---|
| Developer portfolios | Skills, projects, experience, education, certificates |
| Company profiles & job board | Companies post jobs, developers browse and apply |
| AI CV analysis | Extracts and structures CV data into a consistent format |
| ATS scoring | Scores a CV and returns feedback and improvement tips |
| Semantic search | Finds candidates by meaning using vector embeddings |
| Candidate matching | Ranks candidates against a job description |

---

## My Contribution

### Frontend (React.js)
- Built [X] pages, including developer and company flows
- Created reusable components and responsive layouts with Tailwind CSS
- Integrated the Laravel REST API using Axios
- Managed async states: loading, errors, and long-running AI results
- [Add one specific challenge you solved, e.g. showing ATS results without blocking the UI]

### AI & Automation (n8n)
- **CV processing:** PDF text extraction, then structured JSON output through OpenAI
- **ATS scoring:** Prompt-engineered scoring with structured output and improvement suggestions
- **Candidate indexing:** Embeddings generated with `[embedding model]` and stored in Pinecone
- **Semantic search:** Vector query with top-k = `[X]`, then reranking with Cohere `[keep only if used]`
- **Matching:** GPT-generated explanation for why each candidate matches
- **Async design:** Webhook-triggered workflows so the client is never blocked

---

## Architecture

```text
React Frontend ──► Laravel REST API ──► MySQL
                         │
                         ▼
                  n8n Webhooks
                         │
        ┌────────────────┼─────────────────┐
        ▼                ▼                 ▼
   CV Analysis      ATS Scoring     Embeddings ──► Pinecone
     (OpenAI)        (OpenAI)                          │
                                                       ▼
                                      Semantic Search ──► Rerank ──► Match Report
```

---

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React.js, JavaScript, Tailwind CSS, Axios |
| Backend (teammate) | Laravel, MySQL, REST API, RBAC |
| AI & Automation | n8n, OpenAI, Webhooks |
| Retrieval | Pinecone, Vector Embeddings, Cohere Reranker `[if used]` |

---

## Results

<!-- Fill with real numbers from your own testing, or delete this section -->

| Metric | Value |
|---|---|
| CVs tested | [X] |
| Average processing time per CV | [X] seconds |
| Search quality vs keyword search | [describe how you compared] |

---

## Team

| Name | Role |
|---|---|
| **Mohammed AL Bzoor** | Frontend, API integration, AI pipelines |
| **Abdalrhman Hamed** | Backend, system architecture, frontend |

---

## Repository Status

This repository documents my contribution to TechNetwork. The core application source code is private due to academic project requirements. The AI workflows are public for technical review:
👉 [n8n workflows](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks)

---

## Author

**Mohammed AL Bzoor** — Full Stack Developer (React, Node.js, AI Automation)
Computer Science, Al al-Bayt University, [graduation year]

[GitHub](https://github.com/mohammadbzoor) • [LinkedIn](https://www.linkedin.com/in/mohammadbzoor) • [Portfolio](https://profaile-19e99.web.app/)
