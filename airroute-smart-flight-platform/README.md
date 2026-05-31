<div align="center">

# AIrRoute - Smart Flight Platform

### A smart flight discovery and booking concept built during Build with AI Hackathon

AIrRoute is a frontend-focused smart flight platform concept designed to unify Jordanian airline flight options in one place, making it easier for users to browse flights, compare prices, and simplify the booking experience.

<br />

![React](https://img.shields.io/badge/React.js-Frontend-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-Responsive%20UI-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-Chatbot%20Integration-4285F4?style=for-the-badge\&logo=google\&logoColor=white)
![Hackathon](https://img.shields.io/badge/Build%20with%20AI-Hackathon-purple?style=for-the-badge)

</div>

---

## Overview

**AIrRoute** is a smart flight platform concept developed during the **Build with AI Hackathon**.

The idea was to build a unified platform that gathers Jordanian airline flight options in one place, allowing users to browse available flights, compare prices, and interact with a smart chatbot that helps answer flight-related questions.

The project focused on creating a practical and sustainable AI-assisted travel experience while also reducing unnecessary API calls by preparing a custom dataset for the chatbot.

---

## Project Idea

The platform was designed to solve a simple but real problem:

> Travelers often need to check multiple airline websites to compare flights and prices.

AIrRoute aims to simplify this process by offering one interface where users can:

* Browse Jordanian airline flights
* Compare prices
* View flight details
* Use smart search and filtering
* Interact with a chatbot for instant help
* Experience a cleaner and faster flight discovery flow

---

## Frontend Structure

```text
src/
├── components/
│   ├── ui/
│   │   ├── FlightCard
│   │   ├── AiSearchBox
│   │   ├── FlightsFilters
│   │   └── FlightsGrid
│   │
│   ├── layout/
│   │   ├── MainNavbar
│   │   └── Sidebar
│   │
│   └── features/
│       ├── SmartChat
│       ├── FlightsChat
│       └── ResultsSummary
│
├── pages/
│   ├── Home.js
│   ├── Flights.js
│   ├── Airlines.js
│   ├── CreateFlight.js
│   ├── DataManager.js
│   └── SmartDataChat.js
│
└── styles/
    ├── components/
    └── pages/
```

---

## Main Features

| Feature            | Description                                                              |
| ------------------ | ------------------------------------------------------------------------ |
| Flight Discovery   | Allows users to browse available flights in a unified interface          |
| Price Comparison   | Helps users compare flight options and prices                            |
| Smart Chatbot      | Provides instant answers to flight-related questions                     |
| Custom Dataset     | Reduces direct API calls by relying on prepared data where possible      |
| Flight Cards       | Displays flight details using reusable UI cards                          |
| Smart Search Box   | Supports intelligent flight search interactions                          |
| Flight Filters     | Allows users to filter flight results                                    |
| Flights Grid       | Displays flight results in an organized responsive layout                |
| Airlines Page      | Shows available airlines                                                 |
| Create Flight Page | Supports adding flight data during prototype/demo flow                   |
| Data Manager       | Helps manage structured flight-related data                              |
| Arabic UI Support  | Interface and project experience were designed with Arabic users in mind |

---

## Main Pages

| Page            | Description                                                   |
| --------------- | ------------------------------------------------------------- |
| Home            | Landing page for the platform and flight discovery experience |
| Flights         | Displays available flights and search results                 |
| Airlines        | Shows airline companies available in the platform             |
| Create Flight   | Form for adding new flight data                               |
| Data Manager    | Page for managing flight-related data                         |
| Smart Data Chat | Smart chatbot interface for flight-related questions          |

---

## Main Components

| Component      | Description                                            |
| -------------- | ------------------------------------------------------ |
| MainNavbar     | Top navigation bar with branding and navigation links  |
| Sidebar        | Collapsible sidebar for navigation                     |
| FlightCard     | Reusable card for displaying flight information        |
| AiSearchBox    | Smart search input for flight discovery                |
| FlightsFilters | Filtering controls for flight results                  |
| FlightsGrid    | Responsive grid layout for displaying multiple flights |
| SmartChat      | Chatbot component for user assistance                  |
| FlightsChat    | Flight-focused chat interaction component              |
| ResultsSummary | Displays summarized search or chatbot results          |

---

## AI Chatbot Approach

To enhance the platform, the team added a smart chatbot that helps users answer questions instantly.

Because direct API calls connected with Gemini can become costly, the team prepared a custom dataset to reduce unnecessary live API requests, improve response efficiency, and make the solution more practical for real-world use.

The chatbot idea focused on:

* Answering flight-related questions
* Helping users understand available options
* Supporting search and discovery
* Reducing API dependency through prepared data
* Improving performance and cost efficiency

---

## Tech Stack

<div align="center">

![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge\&logo=react\&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap%205-7952B3?style=for-the-badge\&logo=bootstrap\&logoColor=white)
![React Router](https://img.shields.io/badge/React%20Router-Routing-CA4245?style=for-the-badge\&logo=react-router\&logoColor=white)
![Font Awesome](https://img.shields.io/badge/Font%20Awesome-Icons-528DD7?style=for-the-badge\&logo=fontawesome\&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-Chatbot%20API-4285F4?style=for-the-badge\&logo=google\&logoColor=white)

</div>

---

## Design and UI

The frontend was structured with a clear separation between:

* Reusable UI components
* Layout components
* Feature-specific components
* Application pages
* Component-level and page-level styles

The design focused on:

* Clean Arabic user experience
* Responsive layout
* Easy flight browsing
* Organized flight cards
* Clear navigation
* Smart assistant interaction
* Maintainable component structure

---

## My Contribution

My contribution focused on the frontend structure, UI organization, and smart assistant experience within the hackathon project.

Key contribution areas:

| Area               | Contribution                                                             |
| ------------------ | ------------------------------------------------------------------------ |
| Frontend Structure | Worked with a clean React component/page organization                    |
| UI Components      | Supported reusable components such as flight cards, filters, and grids   |
| User Experience    | Helped create a smoother flight browsing and discovery flow              |
| Smart Chatbot      | Supported the chatbot concept and dataset-based response approach        |
| Arabic Interface   | Contributed to a user experience suitable for Arabic-speaking users      |
| Team Collaboration | Worked with the team to turn the hackathon idea into a working prototype |

---

## Hackathon Experience

This project was built as part of **Build with AI Hackathon** with team **AIrRoute**.

The experience included:

* Team-based ideation
* Rapid prototyping
* Building an AI-assisted travel concept
* Designing a practical chatbot approach
* Working under time constraints
* Presenting a solution focused on usability and sustainability

---

## What I Learned

Through this project, I practiced and improved my skills in:

* Building frontend prototypes quickly
* Structuring React projects
* Designing reusable UI components
* Creating responsive layouts with Bootstrap
* Working on AI-assisted product ideas
* Thinking about API cost optimization
* Collaborating in a hackathon team environment
* Turning an idea into a functional prototype

---

## Future Improvements

* Add real flight API integration
* Add authentication for users
* Add booking flow
* Add payment integration
* Add airline admin dashboard
* Add saved flights and user preferences
* Improve chatbot response quality
* Add multilingual support
* Improve search and filtering logic
* Add deployment and live demo

---

## Repository Status

This documentation is public and created for portfolio and project presentation purposes.

The project represents a hackathon prototype focused on smart flight discovery, Jordanian airline aggregation, price comparison, and AI-assisted user support.

---

## Author

<div align="center">

### Mohammed AL Bzoor

**Full Stack Developer | React & AI Automation Engineer**

[![GitHub](https://img.shields.io/badge/GitHub-mohammadbzoor-181717?style=for-the-badge\&logo=github)](https://github.com/mohammadbzoor)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohammed%20AL%20Bzoor-0A66C2?style=for-the-badge\&logo=linkedin)](https://www.linkedin.com/in/mohammadbzoor)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live%20Website-brightgreen?style=for-the-badge)](https://profaile-19e99.web.app/)

</div>
