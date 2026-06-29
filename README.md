# Opportunity Cost

A financial decision-making app that helps you classify needs vs wants, understand opportunity costs, and rank spending priorities.

## Tech Stack

- **Backend:** FastAPI + Python 3.11
- **Database:** PostgreSQL (Supabase) + SQLAlchemy + Alembic
- **Frontend:** Next.js 14 (App Router) + React 18 + TailwindCSS v3
- **Auth:** JWT (python-jose + passlib)
- **LLM:** GPT-4o-mini (with rule-based fallback)

## Local Development

### Prerequisites
- Python 3.11
- Node.js 20 LTS
- A Supabase project (free tier works)

### Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/Pingwyd/opportunity-cost.git
   cd opportunity-cost
   ```

2. Backend setup:
   ```bash
   cd backend
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   ```

3. Create `.env` in project root:
   ```
   DATABASE_URL=postgresql://postgres.[ref]:[password]@aws-0-[region].pooler.supabase.com:6543/postgres
   SECRET_KEY=your-random-secret-key
   OPENAI_API_KEY=sk-your-openai-key
   ```

4. Run migrations:
   ```bash
   cd backend
   alembic upgrade head
   ```

5. Start the backend:
   ```bash
   uvicorn app.main:app --reload
   ```

6. Start the frontend (new terminal):
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

7. Open http://localhost:3000

### Running Tests
```bash
# Backend
cd backend && pytest

# Frontend
cd frontend && npx vitest run
```

### Linting
```bash
# Backend
ruff check backend/
black backend/

# Frontend
cd frontend && npm run lint
cd frontend && npx prettier --write src/
```
