<div align="center">

# TechNetwork: Frontend Development

### React.js frontend for the TechNetwork recruitment platform

[![React](https://img.shields.io/badge/React.js-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-Styling-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

[![Back to Overview](https://img.shields.io/badge/Back%20to-Overview-purple?style=for-the-badge)](./README.md)
[![AI Pipelines](https://img.shields.io/badge/View-AI%20Pipelines-orange?style=for-the-badge)](./ai-pipelines.md)

</div>

---

## Overview

The TechNetwork frontend is a React.js single-page application used by developers and companies. It connects to the Laravel REST API and displays the results of the AI workflows (CV analysis and candidate matching).

I worked on the frontend together with my teammate, and I also built the AI pipelines described in [AI Pipelines](./ai-pipelines.md).

---

## What I Built

| Area | Description |
|---|---|
| Developer pages | Profile views with skills, projects, experience, and certificates |
| Company pages | Company-facing views for browsing developers and recruitment data |
| Job board | Job browsing and application interfaces |
| AI results | Display of ATS score, strengths, weaknesses, and recommendations from CV analysis, and ranked candidate matches from semantic search |
| Reusable components | Shared UI components used across pages to keep the code organized |
| Responsive layouts | Layouts that adapt to different screen sizes, using Tailwind CSS and custom CSS |

---

## API Integration

- Connected the interface to the Laravel REST API using Axios
- Handled loading and response states in the UI
- Displayed JSON responses from the AI workflows, such as the ATS analysis result and ranked candidate matches

---

## Tech Stack

| Category | Tools |
|---|---|
| Framework | React.js, JavaScript |
| Styling | Tailwind CSS, Custom CSS |
| API | Axios, REST APIs |
| Tools | Git, GitHub |

---

## What I Learned

- Building a real-world React application as part of a team
- Structuring reusable components and presenting API data clearly
- Displaying AI-generated output inside a user interface

---

## Related Documentation

- [Back to Overview](./README.md)
- [AI Pipelines](./ai-pipelines.md)
