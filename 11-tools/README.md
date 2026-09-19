# Module 11: Developer Tools, Cloud & MLOps

> Master the industry-standard developer workflow: Git & GitHub, interactive cloud environments (Colab/Kaggle), containerization with Docker, and serving models via FastAPI and Streamlit.

---

## 📋 Prerequisites
- Module 01 (Python and command-line basics).

---

## 🧠 Core Concepts

1. **Version Control with Git & GitHub:**
   - Tracking changes, staging (`git add`), and committing (`git commit`).
   - Branching workflows (`git checkout -b feature-branch`).
   - Merge conflicts and rebasing.
   - Remote repositories, forks, and pull requests.
   - `.gitignore` best practices for machine learning (excluding large `.ckpt`, `.pt`, `.pkl`, and raw data directories).
2. **Cloud Notebook Environments:**
   - **Google Colab:** Free GPU/TPU hardware acceleration, mounting Google Drive, installing packages with `!pip install`.
   - **Kaggle Kernels:** Working directly with competition datasets and public community notebooks.
3. **Serving Machine Learning Models:**
   - **FastAPI:** Building high-performance, asynchronous REST API endpoints with automatic Swagger documentation.
   - Pydantic models for strict input validation and data schemas.
   - **Streamlit / Gradio:** Rapidly prototyping interactive web UIs in pure Python for model demonstrations.
4. **Containerization with Docker:**
   - Why containerization solves "works on my machine" issues.
   - Writing clean `Dockerfile` recipes: Base image, copying files, installing dependencies, exposing ports, and `CMD`.
   - Building and running containers locally.

---

## 🗺️ Recommended Sequence

1. Read the [Pro Git Book (Chapters 1–3)](https://git-scm.com/book/en/v2).
2. Read the [FastAPI First Steps Tutorial](https://fastapi.tiangolo.com/tutorial/first-steps/).
3. Follow the [Streamlit Getting Started Guide](https://docs.streamlit.io/get-started).
4. Build and containerize a simple inference API.

---

## 💻 Practical Exercises

### Exercise: Minimal FastAPI Prediction Endpoint
```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI(title="AIML Model Serving Demo")

class ModelInput(BaseModel):
    feature_1: float
    feature_2: float

class ModelOutput(BaseModel):
    prediction: float
    status: str

@app.get("/")
def health_check():
    return {"status": "healthy", "service": "AIML Club Prediction Engine"}

@app.post("/predict", response_model=ModelOutput)
def predict(data: ModelInput):
    # Mock inference calculation
    result = data.feature_1 * 0.5 + data.feature_2 * 1.2
    return ModelOutput(prediction=result, status="success")
```

Run with: `uvicorn main:app --reload`

---

## 💡 Project Ideas
- **Self-Contained ML Microservice:** Package a trained sentiment analysis model into a Docker container serving predictions over a FastAPI endpoint with Swagger docs.
- **Interactive Model Playground:** Build a Streamlit dashboard that lets users upload custom images and view object detection bounding boxes rendered in real time.

---

## 📖 Official Documentation & Resources
- 📖 [Git Official Documentation](https://git-scm.com/doc)
- 📖 [FastAPI Official Documentation](https://fastapi.tiangolo.com/)
- 📖 [Streamlit Documentation](https://docs.streamlit.io/)
- 📖 [Docker Documentation](https://docs.docker.com/)
