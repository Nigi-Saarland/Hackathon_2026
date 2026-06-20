# Interview Copilot — Kohlpharma GmbH
AI-powered interview assistant for non-technical hiring managers.

---

## What this does
1. **Generate Interview Guide** — Paste a job title + description, get a full interview kit with questions, what to listen for, and red flags.
2. **Analyze Candidate Answers** — Paste what a candidate said, get a green/yellow/red rating and a follow-up question to dig deeper.

---

## Setup (one time)

### 1. Add your Gemini API key
Open `server/index.js` and replace:
```
const GEMINI_API_KEY = "YOUR_GEMINI_API_KEY_HERE";
```
with your actual key.

### 2. Install and start the backend
```bash
cd server
npm install
node index.js
```
You should see: `Server running on http://localhost:3001`

### 3. Install and start the frontend (new terminal)
```bash
cd client
npm install
npm start
```
Browser opens automatically at `http://localhost:3000`

---

## Project structure
```
interview-support/
├── server/
│   ├── index.js        ← Express backend + Gemini API calls
│   └── package.json
└── client/
    ├── src/
│   │   ├── App.js      ← React UI
│   │   ├── App.css     ← Styles
│   │   └── index.js    ← Entry point
    └── public/
        └── index.html
```

---

## Notes
- Both terminals must be running at the same time.
- The `proxy` in `client/package.json` routes `/api/*` calls to the backend automatically.
- To print or save the interview guide as PDF: use the "Print / Save as PDF" button.
