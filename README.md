
# 🤖 AI-Driven Skill Gap & Job Market Forecasting System

> An end-to-end AI/ML pipeline that extracts skills from job descriptions,
> scores candidate-job alignment semantically, predicts job readiness using
> machine learning, and forecasts future skill demand trends using time-series models.

---

## 🚀 Live Demo

Run locally → `http://localhost:8000/docs`

---

## 📌 Features

- 🔍 **Skill Extraction** — Extracts and normalises skills from raw text using TF-IDF + regex + alias mapping
- 🤝 **Semantic Matching** — Scores candidate-job alignment using Jaccard similarity + TF-IDF cosine similarity
- 🎯 **Job Readiness Scoring** — Predicts readiness label (Not Ready / Partially Ready / Ready) using Random Forest & Gradient Boosting
- 📈 **Demand Forecasting** — Forecasts monthly skill demand using ARIMA and Facebook Prophet (auto-selects best model by MAPE)
- ⚡ **REST API** — All features exposed as clean FastAPI JSON endpoints

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Language | Python 3.11 |
| API | FastAPI + Uvicorn |
| NLP | TF-IDF, Regex, Alias Normalisation |
| ML Models | Random Forest, Gradient Boosting, Logistic Regression |
| Forecasting | ARIMA (statsmodels), Facebook Prophet |
| Deployment | Docker, docker-compose |

---

## 📂 Project Structure
```
skill_gap_system.py   ← Single-file, full project
requirements.txt      ← All dependencies
HOW_TO_RUN.txt        ← Quick start guide
```

---

## ⚙️ Installation & Run
```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/skill-gap-forecasting.git
cd skill-gap-forecasting

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the API
python skill_gap_system.py

# 4. Open interactive docs
# http://localhost:8000/docs
```

---

## 🔗 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Health check |
| POST | `/extract-skills` | Extract skills from raw text |
| POST | `/match` | Candidate ↔ Job semantic match score |
| POST | `/readiness` | ML-based job readiness prediction |
| GET | `/forecast/{skill}` | ARIMA / Prophet demand forecast |
| GET | `/trending` | Top trending skills by growth rate |
| POST | `/full-analysis` | All-in-one pipeline |

---

## 📊 Sample Output — Full Analysis
```json
{
  "step_1_extracted": {
    "candidate_skills": ["FastAPI", "LangChain", "Machine Learning", "Python", "RAG"],
    "job_skills": ["Docker", "LangChain", "Python", "RAG", "SQL"]
  },
  "step_2_match": {
    "composite_score": 0.4975,
    "matched_skills": ["LangChain", "Python", "RAG"],
    "missing_skills": ["Docker", "SQL"],
    "match_pct": 60.0
  },
  "step_3_readiness": {
    "readiness_label": "Ready",
    "confidence": 0.84
  },
  "step_4_forecast": {
    "skill": "Python",
    "best_model": "Prophet",
    "forecast_values": [312, 318, 325],
    "trend": "rising"
  }
}
```

---

## 🐳 Docker Deployment
```bash
docker-compose up --build
# API available at http://localhost:8000
```

---

## 👤 Author

**Shanmugakumar L**
B.Tech — Artificial Intelligence & Data Science
Jansons Institute of Technology, Coimbatore

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/YOUR_PROFILE)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/YOUR_USERNAME)

---

## 📜 License

MIT License — feel free to use, modify, and distribute.
