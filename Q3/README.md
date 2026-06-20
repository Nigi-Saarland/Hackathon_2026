# Work Permit Validator
**Leistenschneider Personaldienstleistungen GmbH**

AI-powered work permit document validation using Google Gemini.

---

## Setup

### 1. Prerequisites
- Node.js 18+ installed
- A Google Gemini API key

### 2. Configure the backend

```bash
cd backend
cp .env.example .env
```

Open `backend/.env` and add your Gemini API key:
```
GEMINI_API_KEY=your_actual_key_here
PORT=3001
```

### 3. Install & run the backend

```bash
cd backend
npm install
npm start
```

The backend starts at **http://localhost:3001**

### 4. Install & run the frontend (new terminal)

```bash
cd frontend
npm install
npm start
```

The app opens at **http://localhost:3000**

---

## Usage

1. Open **http://localhost:3000** in your browser
2. Drag & drop PDF work permit files onto the upload area (or click to browse)
3. Multiple files can be uploaded at once
4. Results appear with:
   - ✓ / ✗ Valid or Invalid determination
   - Confidence percentage (0–100%)
   - Valid-until date
   - Permit type, issuing country, holder name
   - Key findings from the AI analysis

---

## How it works

Each PDF is sent to the **Gemini 2.0 Flash Lite** model which:
- Reads the full document content
- Looks for official government markings, permit numbers, issuing authority, dates
- Returns a structured JSON result with confidence score and extracted data

---

## Notes

- Only PDF files are accepted
- Max file size: 20MB per file
- The AI confidence score reflects how certain the model is — scores below 60% should be reviewed manually
- Always confirm with original documents for legally binding decisions
