# Memora AI

Memora AI is a starter full-stack workspace for uploading documents, chunking and summarizing memory content, retrieving answers, and exploring graph relationships.

## Structure

- `frontend/`: Streamlit app and pages.
- `backend/`: FastAPI app, routes, services, agents, database adapters, and utilities.
- `data/`: Local upload and processed chunk placeholders.
- `docker/`: Dockerfiles for frontend and backend services.

## Run Locally

Install dependencies and make sure PostgreSQL is running:

```powershell
pip install -r requirements.txt
```

Configure the local database in `.env`:

```text
POSTGRES_DSN=postgresql://memora:memora@localhost:5433/memora
```

The API loads this file automatically when it starts.

Run the API:

```powershell
cd backend
uvicorn main:app --reload
```

Run the frontend in a second terminal:

```powershell
cd frontend
streamlit run app.py
```

## Docker

```powershell
docker compose up --build
```

Docker Compose starts PostgreSQL, the API, and the frontend. PostgreSQL data is
kept in the `postgres_data` Docker volume between restarts.
