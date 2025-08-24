# Kyle Spengler — ML Engineer (Contract)
I ship production-ready ML APIs you can run in minutes: FastAPI, API-key auth, rate limits, p50/p95 metrics, CI, and a Docker image on GHCR.

![Python](https://img.shields.io/badge/Python-3.11-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-API%20First-teal)
![Docker](https://img.shields.io/badge/Docker-Prod%20Images-informational)
![CI](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-181717)

---

## What I do
- Design and ship **production-style ML microservices** (FastAPI + Uvicorn)
- Add **API-key auth** & **token-bucket rate limiting**
- Instrument `/metrics` (p50/p95) plus `/health` and `/version`
- Build reproducible **Docker images** and publish to **GHCR**
- Wire up **CI smoke tests** (boot server → hit health → assert JSON)
## What I’m looking for
- Contract ML Engineer (remote, US-friendly time zones)
- 10–25 hrs/week, 1–3 week sprints, or full time
- ML APIs (FastAPI), RAG baselines, Docker, CI/CD
- Start: immediately · Contact: kyle.s.delivery@gmail.com · [LinkedIn](https://www.linkedin.com/in/kyle-spengler-30b186355/)



---

## Projects you can try in minutes

### 1) ML Serving App (FastAPI + scikit-learn)
Repo → **[serving_app](https://github.com/KyleSDeveloper/serving_app)** · Image → **ghcr.io/kylesdeveloper/serving_app:latest**

```bash
# Run the container
docker run --rm -p 8011:8000 ghcr.io/kylesdeveloper/serving_app:latest

# Health & version
curl -s http://localhost:8011/health  | python -m json.tool
curl -s http://localhost:8011/version

# Single prediction
curl -s -X POST http://localhost:8011/predict \
  -H 'Content-Type: application/json' \
  -d '{"features":[5.1,3.5,1.4,0.2], "return_proba": true}' | python -m json.tool
```
What’s inside: Pydantic schemas, /predict & /predict_batch, /health & /version, CI that boots the API and hits /health.

### 2) Production RAG Service — Starter Kit
Repo → **[rag_service](https://github.com/KyleSDeveloper/rag_service)** (FastAPI + BM25 baseline + metrics)

```bash
# Quickstart (local)
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m rag_app.index --corpus ./corpus --out ./rag_app/index.json
API_KEY=dev-key RATE_LIMIT_PER_MIN=30 uvicorn rag_app.main:app --port 8010

# Ask
curl -s -X POST "http://localhost:8010/ask" \
  -H "x-api-key: dev-key" -H "Content-Type: application/json" \
  -d '{"question":"What is coinsurance?","k":5}' | python -m json.tool

# Metrics
curl -s "http://localhost:8010/metrics" | python -m json.tool
```
What’s inside: API-key auth, per-key rate limits, stopword-aware BM25 boosting, /metrics with p50/p95, CI smoke tests, Dockerfile.

## How I work
- Ship early: health/version + one endpoint + metrics first, then iterate
- Automate: CI smoke tests (boot server, hit /health, fetch /metrics)
- Document: clear README with curl examples & troubleshooting
- Own the pipeline: training script → artifact → serving API → image → registry

## Tech I use
Python, FastAPI, Uvicorn, Pydantic, scikit-learn, NumPy, Docker, GitHub Actions, rank-bm25

## Work with me
- Open to: contract / part-time / short engagements
- Areas: ML APIs, retrieval/RAG baselines, metrics & reliability, containerization, CI/CD
- Contact: [kyle.s.delivery@gmail.com](mailto:kyle.s.delivery@gmail.com) · [LinkedIn](https://www.linkedin.com/in/kyle-spengler-30b186355/)

Want something similar for your team? I can clone one of these services to your domain and ship a runnable image with metrics and CI.

## Quick links
- 🔧 Serving App: https://github.com/KyleSDeveloper/serving_app
- 📚 RAG Service: https://github.com/KyleSDeveloper/rag_service





