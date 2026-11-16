# cse4104-7a-t02-ai-email-generator
An AI-powered Email Generator using React And Gemini AI
# AI-Based Email Generator

An AI-powered web application for writing professional, formal and personalized emails. The user enters a recipient, subject and purpose, chooses an email type and tone, and the system generates a complete email using the Google Gemini API. The email can then be rewritten, shortened, expanded, grammar-corrected, copied, downloaded and saved in a searchable history.

**Course:** CSE 4104 – Software Development III (AI-Based Software Project Development)
**Institution:** Northern University of Business and Technology, Khulna – Department of Computer Science and Engineering

---

## Team Information

| Field | Information |
|---|---|
| Team Name | CSE4104-7A-T02 |
| Section | 7A |
| Project Title | AI-Based Email Generator |
| Team Leader | Mehedi Hassan Prince |
| Course Teacher | Md. Riaz Mahmud, Assistant Professor |
| GitHub Repository | https://github.com/<username>/cse4104-7a-t02-ai-email-generator |
| Deployment Link | To be added after deployment |

| No. | Name | Student ID | Role |
|---|---|---|---|
| 1 | Mehedi Hassan Prince (Team Leader) | 11230321512 | Team Leader and Database Manager |
| 2 | Mst. Anamika Islam Santa | 11230321492 | Frontend Developer |
| 3 | Shrabonti Das | 11230321234 | Backend Developer |
| 4 | Sumaia Jannat Tinni | 11230121197 | AI Integration Lead |

---

## Problem Statement

Writing a clear and professional email is difficult for many students, job seekers and office users. They struggle with word choice, formal tone, grammar and structure, and writing recurring emails such as leave applications, job applications, complaints and requests to teachers takes time. Existing tools such as Gemini in Gmail, Grammarly and HubSpot Breeze Assistant are tied to one platform, focus on correcting text instead of generating a complete email, or need a paid plan. This project provides a simple, dedicated and free-to-use alternative.

## Features

| No. | Feature | Description |
|---|---|---|
| 1 | User Authentication | Register and log in with email and password (JWT, bcrypt) or with Google sign-in |
| 2 | AI Email Generation | Generate a complete email from recipient, subject, purpose and type |
| 3 | Multiple Email Types | Academic, job application, business, complaint, request, follow-up and personal |
| 4 | Tone Selection | Formal, friendly and professional |
| 5 | Rewrite and Improve | Improve the structure, clarity and wording of an email |
| 6 | Shorten and Expand | Make an email shorter or more detailed |
| 7 | Grammar Correction | Fix grammar, spelling and sentence structure |
| 8 | Copy and Download | Copy to clipboard or download the email |
| 9 | Email History | Save, view, search and delete previous emails |
| 10 | Responsive Interface | Works on desktop, tablet and mobile |

## Technology Stack

| Category | Technology |
|---|---|
| Frontend | React.js, HTML, CSS |
| Backend | Node.js, Express.js |
| Database | MySQL |
| Authentication | JWT, bcrypt, Google OAuth 2.0 |
| AI Service | Google Gemini API |
| Design and Testing | Figma, Postman |
| Version Control | Git, GitHub |
| Deployment | Vercel (frontend), Render (backend), Railway (MySQL) |

## AI Workflow

```
User Input → React Frontend → Express Backend (builds the prompt) → Gemini API → AI Response → Backend (saves to MySQL) → Frontend displays the email
```

The Gemini API key is stored only on the server in a `.env` file and is never sent to the browser.

## Project Structure

This is the planned structure. Update it as the project grows.

```
cse4104-7a-t02-ai-email-generator/
├── frontend/
├── backend/
├── documentation/
├── screenshots/
└── README.md
```

## Getting Started

### Prerequisites

- Node.js 18 or later and npm
- MySQL 8 or later
- A Google Gemini API key
- A Google OAuth 2.0 client ID

### 1. Clone the repository

```bash
git clone https://github.com/<username>/cse4104-7a-t02-ai-email-generator.git
cd cse4104-7a-t02-ai-email-generator
```

### 2. Set up the database

Create an empty MySQL database and a user for it, then import the schema file once it is added to the backend folder.

```sql
CREATE DATABASE email_generator CHARACTER SET utf8mb4;
```

### 3. Set up the backend

```bash
cd backend
npm install
```

Create a file named `.env` in the `backend` folder:

```env
PORT=5000
DB_HOST=localhost
DB_PORT=3306
DB_USER=your_mysql_user
DB_PASSWORD=your_mysql_password
DB_NAME=email_generator
JWT_SECRET=a_long_random_secret
JWT_EXPIRES_IN=1d
GEMINI_API_KEY=your_gemini_api_key
GOOGLE_CLIENT_ID=your_google_client_id
FRONTEND_URL=http://localhost:3000
```

Start the backend:

```bash
npm run dev
```

### 4. Set up the frontend

```bash
cd frontend
npm install
```

Create a file named `.env` in the `frontend` folder:

```env
VITE_API_URL=http://localhost:5000/api
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

Start the frontend:

```bash
npm run dev
```

Open the address printed in the terminal. The variable names above depend on the frontend tooling the team chooses (for example `REACT_APP_` instead of `VITE_`), so adjust them to match.

> Never commit `.env` files. Add `.env` to `.gitignore`.

## API Overview (proposed)

| Endpoint | Method | Purpose |
|---|---|---|
| `/api/auth/register` | POST | Create an account |
| `/api/auth/login` | POST | Log in with email and password |
| `/api/auth/google` | POST | Log in with a Google token |
| `/api/auth/me` | GET | Get the current user |
| `/api/emails/generate` | POST | Generate a new email |
| `/api/emails/:id/rewrite`, `/shorten`, `/expand`, `/grammar` | POST | Improve an existing email |
| `/api/emails` | GET | List emails (search and type filter) |
| `/api/emails/:id` | GET, PUT, DELETE | View, update or delete one email |

The final API structure will be documented in the API documentation (Week 12).

## Deployment

| Part | Platform | Link |
|---|---|---|
| Frontend | Vercel | To be added |
| Backend | Render | To be added |
| Database | Railway (MySQL) | Not public |

## Screenshots

Screenshots will be added after the UI is built (Week 7).

| Page | Screenshot |
|---|---|
| Login / Register | `screenshots/login.png` |
| Email Generator | `screenshots/generator.png` |
| Email History | `screenshots/history.png` |

## Documentation

| Document | Week | Location |
|---|---|---|
| Project Proposal | 2 | `documentation/` |
| SRS | 3 | `documentation/` |
| Use Case, ER and Architecture Diagrams | 3–4 | `documentation/` |
| Figma Designs | 5 | `documentation/` |
| Testing Report | 10 | `documentation/` |
| Final Report, User Manual, API Documentation | 12 | `documentation/` |

## Git Workflow

| Branch | Purpose |
|---|---|
| `main` | Stable, deployed code |
| `development` | Integration of finished features |
| `frontend` | React interface |
| `backend` | API, authentication and database |
| `ai-integration` | Gemini integration and prompts |

Commit messages should describe the change, for example `Added JWT authentication` or `Implemented email generation API`.

## Limitations

- Generated emails are drafts. Users must review the text before using it.
- The system does not send emails and does not connect to Gmail or Outlook.
- AI output quality depends on the Gemini API and on how clear the user's inputs are.

## Acknowledgements

Course: CSE 4104 – Software Development III. Instructor: Md. Riaz Mahmud, Assistant Professor, Department of CSE, NUBT Khulna.
