# Alpha — Backend & AI Automation

> **One wrong number in an expense can affect an entire financial system.**

Alpha is a smart personal finance platform designed to help users understand, organize, and manage their financial life through financial cycles, savings allocation, financial goals, AI assistance, voice input, receipt OCR, and financial analysis.

🔗 **Project Repository:** [https://github.com/mohammadbzoor/AlphaAPP](https://github.com/mohammadbzoor/AlphaAPP)

## 👨‍💻 My Contribution

My main contribution to Alpha was focused on the **Backend** and the **AI automation layer using n8n**.

I worked primarily with **Node.js, Express.js, MySQL, REST APIs, financial business logic, database transactions, concurrency control, n8n, and OpenAI models**.

Working on Alpha taught me one of the most important engineering principles I have learned:

> **Understand the logic before you implement the code.**

In a financial system, the biggest challenge is not simply writing endpoints or connecting a database. The real challenge is understanding how every financial value is connected to the others.

Before implementing the backend logic, I had to understand questions such as:

* What exactly does a financial cycle represent?
* Why does savings allocation need to happen in a specific order?
* How is the emergency fund funded without affecting other commitments?
* How do financial goals remain consistent when they are edited, reallocated, deferred, or executed?
* What happens when income changes?
* What happens when an expense exceeds the budget?
* How can the system remain consistent when two operations happen at the same time?

In a financial application:

**One number changes → related calculations change → other financial values are affected → the entire financial state must remain consistent.**

That is why I focused on understanding the relationships and business rules before translating them into code.

---

## 🏗️ Backend Engineering

The backend is built with **Node.js and Express.js** and follows a layered architecture that separates API handling from financial business logic and database operations.

The general structure is:

**Routes → Controllers → Services / Business Logic → Repositories / Data Access → MySQL**

This separation helped keep the financial rules inside dedicated services instead of spreading them across API routes.

### Technologies I Worked With

* Node.js
* Express.js
* MySQL / MySQL2
* JWT Authentication
* bcrypt
* Helmet
* CORS
* express-rate-limit
* express-validator
* Axios
* Vitest

---

## 💰 Financial Business Logic

One of the most important parts of my backend work was implementing and protecting the financial rules behind Alpha.

The system connects several financial concepts:

**Income → Financial Cycle → Fixed Commitments → Available Savings → Emergency Fund / Goals / Unallocated Savings**

Every part depends on the others.

A change in income, expenses, savings, or goals can affect the final financial state, so the backend has to preserve these relationships throughout every operation.

### Financial Cycles

A financial cycle represents the period in which the user's income, expenses, commitments, and savings are tracked.

The cycle follows a defined lifecycle:

**Draft → Active → Settlement Preview → Settlement → Closed**

The backend is responsible for maintaining the correct state throughout this lifecycle and ensuring that balances and allocations remain consistent.

### Savings Allocation

Savings are not treated as independent numbers.

The allocation process considers:

1. Emergency Fund
2. Financial Goal allocations
3. Remaining unallocated savings

The order and relationship between these values matter because changing one allocation can affect the remaining available savings.

### Financial Goals & Ledger

Financial goals are not treated as simple numeric fields.

Each contribution is tracked through a financial ledger, allowing the system to maintain a permanent history of goal-related transactions.

The backend also uses **database transactions and row-level locking** for concurrency-sensitive operations.

For example:

`SELECT ... FOR UPDATE`

This helps protect financial operations when multiple requests attempt to modify related records at the same time.

### Preventing Double Counting

Another important challenge was ensuring that the same amount of money is not counted in multiple places.

The backend therefore treats savings and allocations as a connected accounting system rather than a collection of unrelated totals.

---

# 🤖 n8n & AI Automation

A major part of my backend contribution was building the AI automation layer using **n8n** and connecting the system with **OpenAI models**.

The goal was not simply to add an AI chatbot.

The goal was to make AI understand the user's **actual financial context** and use that context to generate useful responses, insights, and actions.

The general workflow is:

**Alpha Backend → Prepare Financial Context → n8n Workflow → OpenAI Model → Validate / Process Output → Final Response**

Each AI capability is designed as an independent workflow so it can evolve without tightly coupling it to the rest of the system.

---

## 🔔 Smart Financial Notifications

Instead of relying only on static notification templates, Alpha can generate notifications based on the user's current financial situation.

The workflow can be summarized as:

**Financial Data → Context Preparation → n8n Workflow → AI Analysis → Notification Generation → Final Notification**

This allows notifications to be based on the user's actual financial context instead of relying entirely on generic messages.

---

## 💬 Context-Aware Financial Assistant

The financial assistant is built around the user's real financial data.

The backend can prepare context such as:

* Current financial cycle
* Income
* Recent expenses
* Active goals
* Savings
* Spending behavior
* Financial status

The workflow then sends the relevant context to the AI model before generating the response.

This means the assistant is designed to respond based on the user's actual financial state rather than behaving like a generic chatbot with no financial context.

---

## 🔊 Voice Financial Analyst

One of the features I worked on that I consider especially interesting is the **Voice Financial Analyst**.

Instead of only presenting financial analysis as text, the system can transform financial insights into an audio experience.

The workflow is:

**Financial Data → Financial Analysis → AI-Generated Insights → Text Processing → Audio Generation → Audio File → User**

The idea is simple:

> **Financial insights should not always have to be read — they can be listened to.**

---

## 🧾 Automatic Transaction Extraction

Alpha supports multiple ways of converting unstructured input into structured financial data.

### Voice Input

**Voice Recording → Speech-to-Text → AI Entity Extraction → Structured Transaction → User Review → Database**

The extraction process can identify information such as:

* Amount
* Currency
* Category
* Description
* Payment Method

### Receipt Processing

**Receipt Image → OCR → Extracted Text → AI / Data Normalization → Transaction Candidate → User Review → Database**

The review step is important because automatically extracted financial information should be verified before becoming part of the permanent financial record.

---

## 🧩 Modular AI Workflows

Each AI feature follows a modular workflow structure:

**1. Prepare Context
2. Invoke AI Model
3. Validate Output
4. Build Final Response**

This modular approach allows individual features to evolve independently.

For example, the **Chat**, **Notifications**, **Voice Analysis**, and **Transaction Extraction** workflows can each be improved without tightly coupling their implementation to the others.

This became especially useful when working with AI because prompts, models, validation rules, and response structures can evolve independently.

---

# 🔐 Backend Security & Reliability

Because Alpha handles financial information, reliability and security were important parts of the backend.

The backend includes:

* JWT authentication
* Password hashing with bcrypt
* Helmet security headers
* Request validation
* CORS configuration
* Rate limiting
* Parameterized database queries
* Database transactions
* Row-level locking for concurrency-sensitive operations

The goal was not only to make the API functional, but to make financial operations behave predictably under real application conditions.

---

# 🧪 Testing

The backend includes automated tests using **Vitest**.

Testing focuses on important areas such as:

* Financial business logic
* API behavior
* Financial calculations
* Data consistency
* Concurrency-sensitive operations
* Financial invariants

In a financial system, testing is not only about checking whether an endpoint returns a response. It is also about verifying that the underlying financial rules remain correct.

---

# 🧠 What This Project Taught Me

The biggest lesson I took from Alpha was not a specific framework or library.

It was a way of thinking.

Instead of starting with:

> **"I need to create an endpoint."**

I learned to start with:

> **"What should happen financially?"**

Then ask:

* What depends on this value?
* What changes when it changes?
* What happens if the operation fails?
* What happens if two operations happen simultaneously?
* How do I guarantee that the final state remains correct?

Only after answering these questions does the implementation become clear.

> **Understand the system first. Model the relationships. Define the rules. Then write the code.**

This became one of the most valuable habits I took from the project, and it changed the way I approach backend development beyond financial software.

---

# 🏆 Hackathon

Alpha was developed as part of our participation as **Team Alpha**, representing **Al al-Bayt University** at the **FinTech Rally Hackathon 2026**, organized by **Jordan Payments & Clearing Company (JoPACC)** and **JOIN Fincubator**.

Although the hackathon is over, Alpha remains one of the most important projects I have worked on.

It taught me how much difference domain understanding can make when building systems where correctness matters.

---

# 🙏 Acknowledgments

Special thanks to **Dr. Sufian HRAZE** for his guidance in understanding the financial logic and calculation processes behind the system.

And thanks to my Team Alpha teammates:

* **Mariam Abusawwa**
* **Rama Alodat**
* **Mohmmad Aba Zaid**
* **Tabark Abed**

---

# 🔗 Project Repository

## AlphaAPP

**Smart AI-Powered Personal Finance Platform**

[https://github.com/mohammadbzoor/AlphaAPP](https://github.com/mohammadbzoor/AlphaAPP)

---

# 💡 Final Thought

> **What if your finance app understood your data instead of just storing it?**

That question became the starting point for a large part of my backend work on Alpha.

My role was about turning that idea into:

**Financial Logic + Reliable Backend APIs + Consistent Database Operations + Concurrency Protection + AI Context Engineering + n8n Automation**

And the biggest lesson I took from the project is simple:

> **Understand before implementing.**
