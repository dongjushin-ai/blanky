# Blanky

Turns text notes into fill-in-the-blank quizzes, then brings wrong answers back more often.

**Live:** https://blanky-pi.vercel.app

## How it works

1. Upload a `.txt` file (UTF-8 or CP949).
2. The backend picks a key word from each line and blanks it out.
3. Answer by typing or by multiple choice. Results are stored per question, and questions you miss are weighted higher in review.

Word selection is rule-based (stopword filtering and scoring in `backend/quiz.py`), so no AI API key is needed.

## Stack

FastAPI · SQLite · React · Vite

## Run locally

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload
```

```bash
cd frontend
npm install
npm run dev
```

The frontend calls the deployed API by default. To use your local backend, change `API` at the top of `frontend/src/App.jsx`.
