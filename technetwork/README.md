<div align="center">

# TechNetwork

### AI-Powered Recruitment Platform for the Tech Industry

Connects developers and companies through verifiable portfolios, a job board,
AI-based CV analysis, ATS scoring, and semantic candidate search.

![Live Demo](https://img.shields.io/badge/Live%20Demo-TechNetwork-22C55E?style=for-the-badge&logo=googlechrome&logoColor=white)
![React](https://img.shields.io/badge/React.js-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Laravel](https://img.shields.io/badge/Laravel-Backend-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-AI%20Workflows-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-LLM-412991?style=for-the-badge&logo=openai&logoColor=white)
![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Search-000000?style=for-the-badge)

[🌐 Live Platform](https://technetworkfront.laravel.cloud/) •
[🤖 n8n Workflows](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks) •
[💼 LinkedIn](https://www.linkedin.com/in/mohammadbzoor)

</div>

---

## Overview

TechNetwork is a recruitment platform built for the tech industry. It addresses two common problems in tech hiring: developer information scattered across many places, and keyword-based search that misses good candidates.

Developers build structured portfolios with their skills, projects, experience, certificates, and CV. Companies publish jobs and search for candidates using natural language. An AI layer analyzes CVs, calculates ATS scores, and matches candidates by meaning instead of exact keywords.

The project was built as a graduation project at Al al-Bayt University, Faculty of Information Technology, Computer Science Department, under the supervision of Dr. Suhair Bani Ata.

---

## Features

| Feature | Description |
|---|---|
| Developer portfolios | Skills, projects, experience, education, and certificates in one profile |
| Company profiles | Companies manage their presence and interact with developers |
| Job board | Companies publish jobs, developers browse and apply |
| AI CV analysis | Extracts and structures CV data from uploaded PDFs |
| ATS scoring | Returns a score with strengths, weaknesses, and improvement suggestions |
| Semantic search | Finds candidates by meaning using vector embeddings |
| AI recruitment assistant | Recruiters describe the candidate they need in plain language and get ranked matches |
| Role-based access | Four user scopes: Admin, Company, Developer, Guest |

---

## How It Works

The Laravel backend hands heavy AI tasks to **n8n**, which runs them as separate workflows. This keeps the main server responsive during PDF parsing and LLM calls.

### Pipeline A: CV Analysis
A developer uploads a CV (PDF). The workflow validates the file, extracts and cleans the text, generates a hash for the CV, and sends the prepared payload to OpenAI. The response is returned as structured JSON containing an ATS score, strengths, weaknesses, and improvement suggestions.

### Pipeline B: Candidate Indexing
When a profile is created or updated, the workflow fetches the candidate profile, normalizes the text, splits it into chunks, and generates OpenAI embeddings. The vectors are stored in Pinecone.

### Pipeline C: Recruitment Assistant
A company submits a natural-language query, for example "backend developer experienced with Laravel". The workflow generates a query embedding, searches the candidate vectors in Pinecone, reranks the results with AI, and returns ranked candidate matches.

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
                                      Semantic Search ──► Rerank ──► Ranked Matches
```

---

## Backend Design

- **Dynamic RBAC:** permissions are stored in the database and mapped at the module, entity, and action level, so an admin can assign privileges (create, edit, view, and more) from the Admin Dashboard instead of changing code.
- **Normalized relational schema** split into four domains:
  - **Users & Security:** users, roles, role rights, modules, actions
  - **Developers:** profiles, experiences, projects, skills, certificates
  - **Companies & Jobs:** companies, jobs, job postings, applications
  - **AI & Analytics:** CVs, CV analyses, candidate profiles, chat messages

---

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React.js, JavaScript, Tailwind CSS, Axios |
| Backend | Laravel (PHP), MySQL, RESTful APIs, Token-based Auth, RBAC |
| AI & Automation | n8n, OpenAI (chat models and embeddings), Webhooks |
| Retrieval | Pinecone, Vector Embeddings, Semantic Search, AI Reranking |
| Tools | Postman, TablePlus, phpMyAdmin, Git |

---

## Team

| Name | Role |
|---|---|
| **Mohammed AL Bzoor** | Frontend (React), API integration, AI pipelines (n8n, OpenAI, Pinecone) |
| **Abdalrhman Hamed** | Backend, system architecture, frontend |

---

## Repository Status

The core application source code is kept private because of academic project requirements. This repository is a project overview.

The AI workflows behind the platform are public:
👉 [TechNetwork n8n Workflows](https://github.com/mohammadbzoor/n8n-workflos/tree/main/teckNetworks)

---

## Author

**Mohammed AL Bzoor** — Full Stack Developer (React, Node.js, AI Automation)

[GitHub](https://github.com/mohammadbzoor) • [LinkedIn](https://www.linkedin.com/in/mohammadbzoor) • [Portfolio](https://profaile-19e99.web.app/)
