<div align="center">

# Alpha: Backend & AI Automation

### The backend and AI automation behind a personal finance platform where one wrong number breaks the whole picture

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![n8n](https://img.shields.io/badge/n8n-AI%20Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-AI%20Integration-412991?style=for-the-badge&logo=openai&logoColor=white)](https://openai.com/)
[![Vitest](https://img.shields.io/badge/Vitest-Testing-6E9F18?style=for-the-badge&logo=vitest&logoColor=white)](https://vitest.dev/)

[AlphaAPP Repository](https://github.com/mohammadbzoor/AlphaAPP) •
[n8n Workflows](https://github.com/mohammadbzoor/n8n-workflos/tree/main/03_Alpha_Finance)

</div>

---

## Overview

Alpha is a personal finance and budgeting platform built by Team Alpha for the **FinTech Rally Hackathon 2026**, organized by Jordan Payments & Clearing Company (JoPACC) and JOIN Fincubator, representing Al al-Bayt University.

**My role:** the backend (Node.js, Express, MySQL) and the AI automation layer (n8n, OpenAI). The mobile app and other parts were built by my teammates.

In financial software, the hard part is not creating endpoints. It is keeping every number consistent with the others. Income, savings, an emergency fund, and goals are all connected, so a change in one value affects several others.

---

## Financial Model

```text
Income
   │
   ▼
Financial Cycle
   │
   ├── Fixed Commitments
   ├── Emergency Fund
   ├── Financial Goals
   └── Unallocated Savings
```

The backend enforces one core rule so savings are never counted twice:

```text
Unallocated Savings = Planned Savings − Emergency Fund − Σ Goal Allocations
```

A financial cycle moves through a defined lifecycle:

```text
Draft → Active → Settlement Preview → Settlement → Closed
```

Cycles start on a user-defined payday instead of a fixed calendar month, and budgets follow a Needs / Wants / Savings split.

---

## Backend Architecture

A layered architecture keeps business logic separate from the API and the database.

```text
Client → REST API → Routes → Controllers → Services (business logic) → Repositories → MySQL
```

| Technology | Purpose |
|---|---|
| Node.js, Express.js | Runtime and REST API |
| MySQL | Relational database, 26 sequential migration scripts |
| JWT, bcrypt | Authentication and password hashing |
| Helmet, Rate Limiting | HTTP security and request throttling |
| Vitest | Automated tests |

---

## Goals and Ledger

Financial goals are not stored as a single number. Every contribution is an immutable ledger entry, which gives a permanent audit trail.

```text
Financial Goal
      │
      ├── Planned Allocation
      ├── Contributions
      ├── Transactions
      └── Current Balance
```

For operations that modify related records at the same time, the backend uses MySQL transactions with row-level locking:

```sql
SELECT ... FOR UPDATE;
```

This prevents race conditions, for example when the same user changes data from two devices.

---

## AI Automation with n8n

I built the AI layer with n8n and OpenAI models. The goal was for the AI to work with the user's **actual financial context** instead of acting as a generic chatbot.

```text
Alpha Backend
      ↓
Prepare Financial Context
      ↓
n8n Workflow
      ↓
OpenAI Model
      ↓
Validate Output
      ↓
Build Response
      ↓
Alpha Application
```

Each capability is a separate workflow, so prompts, models, and validation rules can change without affecting the others.

| Capability | What it does |
|---|---|
| Financial assistant | Answers using the user's current cycle, income, expenses, goals, and savings |
| Smart notifications | Generates notifications from the user's current financial data |
| Voice financial analyst | Turns financial insights into an audio file |
| Voice to transaction | Speech-to-text, then AI entity extraction into a structured transaction |
| Receipt to transaction | OCR, then normalization into a transaction candidate |

Voice and receipt entries go through a **user review step** before being saved, so extracted data is verified before it becomes part of the permanent record.

---

## Security and Reliability

- JWT authentication
- bcrypt password hashing
- Helmet security headers
- Rate limiting on sensitive and AI endpoints
- Parameterized database queries
- Database transactions with row-level locking

---

## Testing

The backend is tested with Vitest (`npm run test`). The tests cover financial calculations, API behavior, data consistency, concurrency-sensitive operations, and the financial invariants described above.

---

## What I Learned

Instead of starting with "I need an endpoint", I learned to start with "what should happen financially?":

```text
What depends on this value?
What changes when it changes?
What happens if the operation fails?
What happens if two operations run at the same time?
```

Only after answering these did the implementation become clear.

---

## Acknowledgments

Thanks to **Dr. Sufian HRAZE** for guidance on the financial logic and calculations.

Team Alpha: Mariam Abusawwa, Rama Alodat, Mohmmad Aba Zaid, Tabark Abed.

---

<div align="center">

[![AlphaAPP](https://img.shields.io/badge/AlphaAPP-GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mohammadbzoor/AlphaAPP)
[![n8n Workflows](https://img.shields.io/badge/n8n-Workflows-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](https://github.com/mohammadbzoor/n8n-workflos/tree/main/03_Alpha_Finance)

</div>
