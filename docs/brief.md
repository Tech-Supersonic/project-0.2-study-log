# Project 0.2: Study Log - Full Brief

Read this whole file before you write any code. It is written in simple language on purpose. The application is small. The difficulty is in doing it properly, one layer at a time, and being able to explain each layer.

---

## The Problem

You study something most days. Right now you have no record of it. You cannot see what you spent time on, what you keep avoiding, or whether you are getting more confident at anything.

Build a small web application that keeps that record.

## What One Entry Holds

| Field | Type | Example |
|---|---|---|
| id | number | 1 |
| date | date | 2026-08-12 |
| skill | text | React |
| what_i_did | text | Built a component that shows a list |
| minutes | number | 90 |
| confidence | number, 1 to 3 | 2 |

That is the entire data model. One table. It does not grow.

## What The App Does

- Show all entries in a list, newest first
- Add a new entry
- Edit an entry
- Delete an entry
- Filter the list by skill

Nothing else. If you find yourself adding features, stop and go back to the stage you are on.

---

# The Six Stages

Do them in order. Do not jump ahead. Each stage is one branch, one pull request, one recording, and one or more learning log entries.

---

## Stage 1: A page that shows a list

**Branch name:** `stage-1-react-list`

**Build:** A React application with one page. Copy the entries from `seed-data/entries.json` into a list inside your code. Show them on screen in a list, newest first. Show every field. Style it enough that it is readable. Plain CSS is fine.

**Learn first:** What a component is. What JSX is. How to loop over a list and show one item for each thing in it. What props are.

**Done when:** The page runs on your machine and shows all the entries from the seed file.

**Explain in your recording:** What a component is, and where the data on this page is coming from right now.

---

## Stage 2: The data moves to a server

**Branch name:** `stage-2-fastapi-get`

This is the most important stage in the project. Take your time with it.

**Build:** A Python FastAPI application with one endpoint, `GET /entries`, that returns the same entries as a JSON response. Move the entries out of your React code and into a Python list on the server. Change your React page to fetch from that endpoint instead of reading its own list.

**Learn first:** What a server is. What HTTP is. What GET means. What JSON is. What an endpoint is. What it means when the browser "calls" your server.

**Done when:** You run two things at once, the Python server and the React app. The page looks exactly the same as it did in stage 1, but if you stop the Python server, the page stops showing data.

**Explain in your recording:** The page looks identical to last week. So what actually changed, and why does the page break when you stop the server?

That last question is the whole point of this project. If you cannot answer it clearly, do not move to stage 3. Ask for another week on this stage instead. That is a completely acceptable thing to ask for.

---

## Stage 3: The data moves to a database

**Branch name:** `stage-3-sqlite`

**Build:** Create a SQLite database with one table for entries. Load the seed entries into it once. Change your `GET /entries` endpoint to read from the database instead of the Python list. Reading only for now.

**Learn first:** What a database is and why a Python list is not one. What a table, a row, and a column are. What a primary key is. What `SELECT` does.

**Done when:** You stop and restart the Python server and the data is still there. That is the difference a database makes.

**Explain in your recording:** Why did we need a database when the Python list already worked?

---

## Stage 4: Now you can change things

**Branch name:** `stage-4-full-crud`

**Build:** Add three more endpoints: `POST /entries` to create, `PUT /entries/{id}` to update, and `DELETE /entries/{id}` to remove. Then build the React side, a form to add an entry, an edit option on each entry, and a delete button with a confirmation.

Add basic checking on the server: reject an entry with an empty skill, with minutes that are not a positive number, or with a confidence outside one to three.

**Learn first:** What POST, PUT, and DELETE mean and how they differ from GET. What a status code is, at least 200, 201, 400, and 404. Why the server has to check the data even though your form already does.

**Done when:** You can add an entry in the browser, refresh the page, and it is still there. All four actions work.

**Explain in your recording:** Walk through what happens, step by step, from clicking the save button to the new entry appearing in the list.

**From this stage on, use the app for real.** Every study session you do goes in it.

---

## Stage 5: A real database and real settings

**Branch name:** `stage-5-postgres-env`

**Build:** Replace SQLite with PostgreSQL. Move your database connection details out of your code and into environment variables, loaded from a `.env` file. Add `.env` to `.gitignore` and commit a `.env.example` showing the variable names with fake values.

**Learn first:** Why PostgreSQL is used in production when SQLite works fine on your machine. What an environment variable is. Why a password must never be written in code that goes to GitHub.

**Done when:** The app works exactly as before, running against PostgreSQL, and there is no password anywhere in your repository.

**Explain in your recording:** What would go wrong if you committed your real `.env` file to a public repository?

---

## Stage 6: Put it on the internet

**Branch name:** `stage-6-deploy-and-filter`

**Build:** Deploy the frontend and the backend to live URLs, with a hosted PostgreSQL database. Set the environment variables in the hosting platform, not in the code. Then add the last feature, filter the list by skill.

**Learn first:** What is different between running on your machine and running on a server. What CORS is, because you will hit it. Why the frontend needs to know the backend's live address.

**Done when:** You send someone the link, they open it on their phone, and it works. You add an entry from your phone and it is still there tomorrow.

**Explain in your recording:** A four minute walkthrough of the finished application and of how a single entry travels from the form on the screen all the way to the database and back.

---

# Rules You Must Follow

These are not optional and they are the reason this project exists.

## Git

- One branch per stage, named as given above.
- Commit as you work, with messages that say what you did. "Add POST endpoint for entries" is a good message. "Update", "All updated", and "Add files via upload" are not.
- Open a pull request at the end of each stage. Write a description of what you built.
- Wait for review. Do not merge your own pull request.
- Never push directly to main. Never upload files through the GitHub website.

By the end you will have six merged pull requests. If you have fewer, the project is not done regardless of whether the app works.

## Recordings

- One recording per stage, about two minutes, four minutes for the last one.
- Your own voice, answering the explain question for that stage.
- Notes are allowed. Reading a script word for word is not.
- Do not re-record ten times to get it perfect. Being understandable matters more than being polished.

## Learning log

- Fill in `LEARNING_LOG.md` before you open each pull request.
- One row per skill you touched, with a confidence score from one to three and two or three sentences on what clicked and what is still shaky.
- Score honestly. A one is useful information. A two you cannot defend is not.

## Using AI

You may use Claude Code throughout. It will speed you up and you should use it.

The condition is that every pull request description says, in your own words, what you understood and what you did not understand in that stage. If Claude wrote something you cannot explain, say so in the pull request. That is not a failure, it tells us what to teach you next. Claiming to understand something you do not is the only real failure here.

Use the `teach-me` skill before each stage rather than asking for the code straight away.

---

# Definition of Done

- [ ] Live URL that works on someone else's phone
- [ ] Six branches merged through six reviewed pull requests
- [ ] All five actions work: list, add, edit, delete, filter
- [ ] Data survives a restart, and the app runs on PostgreSQL
- [ ] No passwords or secrets anywhere in the repository, `.env.example` committed
- [ ] `LEARNING_LOG.md` filled in, every stage, with confidence scores
- [ ] Six recordings submitted
- [ ] `PRESENTATION.md` filled in
- [ ] A system diagram in `docs/` showing the browser, the server, and the database, and what talks to what
- [ ] Screenshots in `proof/`
- [ ] At least twenty real study entries in the live app, because you actually used it

---

# Review Call

You present on camera. Roughly thirty minutes.

1. Walk through the live application, about five minutes.
2. Explain how one entry travels from the form to the database and back.
3. Open your own code and explain any part we point at.
4. Answer the gap check questions below.

You may keep notes in front of you. English does not need to be perfect. Being understandable does.

---

# Gap Check Questions

If you cannot answer these, you get another project at this same level rather than moving on. That is normal and it is not a punishment.

**Frontend**
1. What is a component, and why split a page into several instead of writing one big one?
2. What is state, and what happens on screen when it changes?

**Backend and APIs**
3. What is the difference between the frontend and the backend, in your own words?
4. What does GET do that POST does not?
5. What does a 404 mean, and what does a 400 mean?
6. Your form already checks the data. Why does the server check it again?

**Data**
7. Why not just keep everything in a Python list?
8. What is a primary key and why does every entry need one?
9. What does SELECT do?

**Shipping**
10. What is an environment variable and why is your database password in one?
11. What is different about running on a server compared with running on your laptop?
12. What is a branch, and what is a pull request?

**The big one**
13. In stage 2 the page looked exactly the same before and after. What actually changed, and why did it matter?
