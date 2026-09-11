<div align="center">

# ⚡ Alpha — Backend & AI Automation

### Building the backend logic behind a financial system where **one wrong number matters.**

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![n8n](https://img.shields.io/badge/n8n-AI%20Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-AI%20Integration-412991?style=for-the-badge&logo=openai&logoColor=white)](https://openai.com/)

<br>

**Backend Engineering • Financial Logic • Database Consistency • AI Automation**

<br>

[🔗 View AlphaAPP Repository](https://github.com/mohammadbzoor/AlphaAPP)

</div>

---

## 👨‍💻 My Role

My main contribution to **Alpha** was focused on the **Backend** and the **AI automation layer using n8n**.

I worked primarily with:

- **Node.js**
- **Express.js**
- **MySQL**
- **REST APIs**
- **Financial business logic**
- **Database transactions**
- **Concurrency control**
- **n8n**
- **OpenAI models**
- **Automated AI workflows**

> ### 🧠 The biggest lesson from Alpha
>
> **Understand the logic before you implement the code.**

In financial software, the difficult part is not simply creating an endpoint or connecting a database.

The real challenge is understanding how every financial value is connected to the others.

---

## 💰 Financial Logic

Alpha is built around interconnected financial concepts:

```text
Income
   │
   ▼
Financial Cycle
   │
   ├── Fixed Commitments
   │
   ├── Emergency Fund
   │
   ├── Financial Goals
   │
   └── Unallocated Savings
````

A change in one value can affect several other calculations.

That meant I had to understand questions such as:

* What exactly does a financial cycle represent?
* In what order should savings be allocated?
* How is the emergency fund funded?
* What happens when income changes?
* What happens when expenses exceed the budget?
* How do financial goals remain consistent after edits or reallocations?
* What happens when two operations modify the same financial data simultaneously?

The core principle was:

```text
One number changes
        ↓
Related calculations change
        ↓
Other financial values are affected
        ↓
The final financial state must remain consistent
```

---

# 🏗️ Backend Architecture

The backend follows a layered architecture designed to keep business logic separated from API and database concerns.

```text
Client
  │
  ▼
REST API
  │
  ▼
Routes
  │
  ▼
Controllers
  │
  ▼
Services / Business Logic
  │
  ▼
Repositories / Data Access
  │
  ▼
MySQL
```

### Core Technologies

| Technology        | Purpose             |
| ----------------- | ------------------- |
| 🟢 **Node.js**    | Backend runtime     |
| ⚫ **Express.js**  | REST API framework  |
| 🔵 **MySQL**      | Relational database |
| 🔐 **JWT**        | Authentication      |
| 🔒 **bcrypt**     | Password hashing    |
| 🛡️ **Helmet**    | HTTP security       |
| 🚦 **Rate Limit** | Request protection  |
| ✅ **Validator**   | Input validation    |
| 🧪 **Vitest**     | Automated testing   |

---

# 🎯 Financial Goals & Ledger

Financial goals are not treated as simple numeric fields.

Each contribution is tracked through a dedicated financial ledger.

```text
Financial Goal
      │
      ├── Planned Allocation
      ├── Contributions
      ├── Transactions
      └── Current Balance
```

For concurrency-sensitive operations, the backend uses database transactions and row-level locking.

```sql
SELECT ... FOR UPDATE;
```

This helps prevent race conditions when multiple operations attempt to modify related financial records simultaneously.

---

# 🛡️ Financial Consistency

One of the most important challenges was preventing financial values from becoming inconsistent or being counted more than once.

The savings system follows a connected model:

```text
Planned Savings
      │
      ├── Emergency Fund
      │
      ├── Goal Allocations
      │
      └── Remaining Unallocated Savings
```

Instead of treating each number independently, the backend maintains the relationships between these values.

---

# 🤖 n8n & AI Automation

A major part of my backend work was building the **AI automation layer using n8n** and connecting Alpha with **OpenAI models**.

The goal was not simply to add AI.

The goal was to make AI understand the user's **actual financial context**.

<div align="center">

### AI Processing Pipeline

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

</div>

Each capability was designed as an independent workflow so it could evolve without tightly coupling the entire AI system.

---

## 🔔 Smart Financial Notifications

Instead of relying only on static templates, Alpha can generate notifications based on the user's current financial context.

```text
Financial Data
      ↓
Context Preparation
      ↓
n8n
      ↓
AI Analysis
      ↓
Notification Generation
      ↓
Final Notification
```

---

## 💬 Context-Aware Financial Assistant

The assistant is designed around the user's actual financial state.

The backend can provide context such as:

| Context            | Example                     |
| ------------------ | --------------------------- |
| 📅 Current Cycle   | Active financial cycle      |
| 💰 Income          | Current income              |
| 💸 Expenses        | Recent spending             |
| 🎯 Goals           | Active financial goals      |
| 🏦 Savings         | Current allocations         |
| 📊 Financial State | Current financial situation |

The workflow then uses this context before generating the final AI response.

This makes the assistant more contextual than a generic chatbot.

---

## 🔊 Voice Financial Analyst

One of the most interesting features I worked on is the **Voice Financial Analyst**.

Instead of presenting financial analysis only as text, the system can transform financial insights into an audio experience.

```text
Financial Data
      ↓
Financial Analysis
      ↓
AI-Generated Insights
      ↓
Text Processing
      ↓
Audio Generation
      ↓
Audio File
      ↓
User
```

> **Financial insights should not always have to be read — they can be listened to.**

---

## 🧾 Automatic Transaction Extraction

Alpha supports converting unstructured input into structured financial transactions.

### 🎤 Voice

```text
Voice Recording
      ↓
Speech-to-Text
      ↓
AI Entity Extraction
      ↓
Structured Transaction
      ↓
User Review
      ↓
Database
```

### 🧾 Receipt

```text
Receipt Image
      ↓
OCR
      ↓
Extracted Text
      ↓
Normalization
      ↓
Transaction Candidate
      ↓
User Review
      ↓
Database
```

The review step ensures that automatically extracted financial information is verified before becoming part of the permanent financial record.

---

# 🧩 Modular AI Workflows

Each AI feature follows the same general architecture:

|   Step | Responsibility       |
| -----: | -------------------- |
| **01** | Prepare Context      |
| **02** | Invoke AI Model      |
| **03** | Validate Output      |
| **04** | Build Final Response |

This modular approach allows:

* Chat to evolve independently
* Notifications to evolve independently
* Voice analysis to evolve independently
* Transaction extraction to evolve independently

This was especially useful because AI prompts, models, validation rules, and response structures can change independently.

---

# 🔐 Security & Reliability

Because Alpha handles financial information, reliability and security were important parts of the backend.

### Implemented Controls

* 🔐 JWT authentication
* 🔒 bcrypt password hashing
* 🛡️ Helmet security headers
* ✅ Input validation
* 🌐 CORS configuration
* 🚦 Rate limiting
* 🗄️ Parameterized database queries
* 🔄 Database transactions
* 🔐 Row-level locking

The goal was not only to make the API work, but to make financial operations behave predictably under real application conditions.

---

# 🧪 Testing

The backend includes automated testing with **Vitest**.

The testing focuses on areas such as:

* Financial business logic
* API behavior
* Calculations
* Data consistency
* Concurrency-sensitive operations
* Financial invariants

---

# 🧠 What Alpha Taught Me

The biggest lesson from Alpha was not a specific framework.

It was a way of thinking.

Instead of starting with:

> *"I need to create an endpoint."*

I learned to start with:

> *"What should happen financially?"*

Then:

```text
What depends on this value?
What changes when it changes?
What happens if the operation fails?
What happens if two operations happen simultaneously?
How do I guarantee that the final state remains correct?
```

Only after understanding these questions does the implementation become clear.

<div align="center">

> **Understand the system first.**
> **Model the relationships.**
> **Define the rules.**
> **Then write the code.**

</div>

---

# 🏆 Hackathon

Alpha was developed as part of our participation as **Team Alpha**, representing **Al al-Bayt University** at the **FinTech Rally Hackathon 2026**, organized by **Jordan Payments & Clearing Company (JoPACC)** and **JOIN Fincubator**.

Although the hackathon is over, Alpha remains one of the most important projects I have worked on.

---

# 🙏 Acknowledgments

Special thanks to **Dr. Sufian HRAZE** for his guidance in understanding the financial logic and calculation processes behind the system.

And thanks to my Team Alpha teammates:

* **Mariam Abusawwa**
* **Rama Alodat**
* **Mohmmad Aba Zaid**
* **Tabark Abed**

---

<div align="center">

## 🔗 Project

### AlphaAPP

**Smart AI-Powered Personal Finance Platform**

[![GitHub](https://img.shields.io/badge/View%20Project-GitHub-181717?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/mohammadbzoor/AlphaAPP)

<br>

### 💡 Final Thought

> **What if your finance app understood your data instead of just storing it?**

<br>

**Backend Engineering • Financial Logic • AI Automation • n8n**

</div>
