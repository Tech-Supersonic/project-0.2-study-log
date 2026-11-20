# Project 0.2: Study Log

| Field | Detail |
|---|---|
| Project Number | 0.2 |
| Project Name | Study Log |
| Tier | Foundations |
| Deadline | 6 weeks from your start date, one stage per week |
| Status | Active |
| Tags | React, Python, FastAPI, REST API, SQL, PostgreSQL, Git Workflow, Pull Requests, Deployment, Environment Management, Technical Explanation |

---

## What This Is

A simple web application where you record what you studied each day.

One entry has five things: the date, the skill you studied, what you did, how many minutes you spent, and a confidence score from one to three. The app lists your entries, lets you add, edit, and delete them, and lets you filter by skill.

That is the whole application. It is meant to be small.

The point of this project is not the app. The point is that you build the same small feature six times, each time one layer deeper, so that by the end you can explain exactly where your data lives, how it gets to the screen, and what every part of a web application is actually doing. Most people learn to copy a full stack app without ever seeing the layers separately. This project separates them on purpose.

You will also use this app for real. Every study session you do from now on goes into it. That means by your review call you will have real data in it and something honest to talk about.

---

## Start Here

**Read [`docs/brief.md`](docs/brief.md) in full before you write any code.** It has the six stages step by step, what each stage must do, the rules you have to follow, and the questions you should be able to answer at the end.

Before you start, add the two provided skills in `skills/` to your Claude project:

- **Learning agent** (`skills/teach-me/SKILL.md`). Say "teach me" and a topic, for example "teach me what a REST API is", and it walks you through it and asks for a confidence score at the end. Save that in `LEARNING_LOG.md`.
- **Troubleshooting agent** (`skills/troubleshoot/SKILL.md`). Describe what broke and it guides you to the cause instead of handing you the fix.

Then fork this repository and work inside your fork. Every stage is delivered as a branch and a pull request. Fill in `PRESENTATION.md` as you go.

Starting data for stage 1 is in [`seed-data/entries.json`](seed-data/entries.json). Use it so you are not typing test data by hand.

---

## The Six Stages

You build the same list of study entries six times. Each stage moves the data one step further from the screen.

| Stage | What you add | Where your data lives at the end |
|---|---|---|
| 1 | A React page that lists entries from a list written in the code | In your JavaScript file |
| 2 | A FastAPI server with one endpoint, and React fetches from it | In a Python list on the server |
| 3 | A SQLite database behind that endpoint | In a real database file |
| 4 | Add, edit, and delete, with forms to drive them | Same database, now you can change it |
| 5 | Move to PostgreSQL, move settings into environment variables | In a managed database |
| 6 | Deploy the whole thing live, add filter by skill | On the internet |

Stage 2 is the most important one. When you finish it, the page on screen will look exactly the same as stage 1. Nothing visible changes. But the data now comes from a server you wrote. Make sure you understand why before you move on, because everything after it depends on that idea.

---

## The Rules

The application is easy on purpose. These rules are the actual project. Work that ignores them is not accepted, even if the app works.

1. **Every stage is a branch and a pull request.** Create a branch, do the stage, open a pull request, get it reviewed, then merge it. Six pull requests by the end. Never push straight to main. Never upload files through the GitHub website.
2. **Every stage ends with a recording.** Two minutes, your own voice, explaining what you added and where your data lives now. Six recordings.
3. **Fill `LEARNING_LOG.md` before you open each pull request.** One entry per skill with a confidence score from one to three. An honest score of one is fine. A missing entry means the pull request does not get merged.
4. **You may use Claude Code.** In each pull request description, write in your own words what you understood and what you did not. Being honest about what you did not understand is part of passing.

---

## Prerequisites

You should already have these from Project 0. If one is rusty, ask your AI Instructor for a fast revision and a few check questions, then move on.

- HTML and CSS basics
- A code editor and a terminal you can navigate
- Git installed, and a GitHub account
- A deployed site, so you have seen deployment once already

You are not expected to know React, Python, FastAPI, or SQL before starting. You learn each of them in the stage where it is needed.

---

## Covered Areas

| Category | Area |
|---|---|
| Programming and Stack Fundamentals | Frontend Development |
| Programming and Stack Fundamentals | Backend Language |
| Programming and Stack Fundamentals | API Construction |
| Programming and Stack Fundamentals | Database Design |
| Programming and Stack Fundamentals | Data Persistence |
| SDLC and Engineering Practices | Version Control |
| SDLC and Engineering Practices | Development Lifecycle |
| SDLC and Engineering Practices | Live Deployment |
| SDLC and Engineering Practices | Secrets and Environment Management |
| Communication and Client Readiness | Technical Explanation |

Communication and Client Readiness is trained through the six recordings and the review call, alongside the build, not as separate work.

---

## Recommended Stack

The stack is fixed for this project. You are learning these specific tools, so do not swap them out.

- **Frontend:** React. Plain React with Vite is enough. Next.js is fine if you already used it in Project 0.
- **Backend:** Python with FastAPI.
- **Database:** SQLite in stage 3, PostgreSQL from stage 5.
- **Deployment:** your choice of free hosting for the frontend and the backend.

There is no AI feature in this project, and that is deliberate. You add AI in Project 1, once the rest of it is solid.

---

## What Is Not In This Project

These are all coming later. Do not add them now, even if you see them in a tutorial.

Login and user accounts, real-time updates, Docker, TypeScript, automated tests, and any AI or LLM feature.
