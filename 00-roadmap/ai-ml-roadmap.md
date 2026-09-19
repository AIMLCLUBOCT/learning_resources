# 🌐 Comprehensive AI/ML Roadmap: Foundations to Production

> The standard full-stack curriculum of AIML Club OCT, bridging theory, deep neural networks, generative AI, and production deployment.

---

## 🧭 Roadmap Overview

```
Phase 1: Foundations ──► Phase 2: Classical ML ──► Phase 3: Deep Learning ──► Phase 4: GenAI & LLMs ──► Phase 5: MLOps
(Python, Math, EDA)      (Scikit-Learn, Trees)    (PyTorch, CNN, RNN)       (Transformers, RAG)        (FastAPI, Docker)
```

---

## Phase 1: Mathematical Foundations & Data Science (Weeks 1–4)
- **Linear Algebra:** Vectors, matrices, vector spaces, dot products, eigenvalues, eigenvectors, Singular Value Decomposition (SVD).
- **Calculus:** Functions, limits, partial derivatives, directional gradients, Jacobian, Hessian matrices, chain rule of calculus.
- **Probability & Statistics:** Random variables, probability distributions (Gaussian, Bernoulli, Poisson), Bayes’ theorem, expectation, variance, hypothesis testing.
- **Tooling:** Python 3.10+, virtual environments, NumPy array computing, Pandas DataFrames, Matplotlib & Seaborn.
- **Modules:** [`01-python`](../01-python/), [`02-mathematics`](../02-mathematics/), [`03-data-science`](../03-data-science/)

---

## Phase 2: Classical Machine Learning (Weeks 5–8)
- **Supervised Learning:**
  - Linear Models: Linear Regression, Ridge, Lasso, Logistic Regression.
  - Non-linear Models: Support Vector Machines (SVMs), k-Nearest Neighbors (k-NN), Decision Trees.
  - Ensemble Methods: Random Forests, Gradient Boosting Machines (XGBoost, LightGBM, CatBoost).
- **Unsupervised Learning:**
  - Clustering: K-Means, DBSCAN, Hierarchical Clustering.
  - Dimensionality Reduction: Principal Component Analysis (PCA), t-SNE.
- **Model Evaluation:**
  - Confusion matrix, ROC-AUC, Precision-Recall curves.
  - Regularization techniques, Cross-validation strategies.
- **Modules:** [`04-machine-learning`](../04-machine-learning/)

---

## Phase 3: Deep Learning & Neural Architectures (Weeks 9–14)
- **Core Deep Learning:**
  - Artificial Neural Networks (ANN), feedforward networks, activation functions (ReLU, Sigmoid, GELU).
  - Backpropagation algorithm, loss functions, optimizers (SGD, Adam, AdamW).
  - PyTorch framework: Tensors, autograd, `nn.Module`, `DataLoader`, custom training loops.
- **Computer Vision (CV):**
  - Convolutional layers, pooling, padding, feature maps.
  - Classic architectures: AlexNet, VGG, ResNet.
  - Object detection: You Only Look Once (YOLO), bounding box regression, IoU.
- **Sequence Modeling & NLP:**
  - Recurrent Neural Networks (RNN), Long Short-Term Memory (LSTM), Gated Recurrent Units (GRU).
  - Word embeddings (Word2Vec, GloVe), tokenization algorithms.
- **Modules:** [`05-deep-learning`](../05-deep-learning/), [`08-computer-vision`](../08-computer-vision/), [`09-nlp`](../09-nlp/)

---

## Phase 4: Generative AI, Large Language Models & AI Agents (Weeks 15–20)
- **The Transformer Architecture:**
  - Scaled dot-product attention, multi-head self-attention, positional encodings.
  - Encoder-only (BERT), Decoder-only (GPT), and Encoder-Decoder (T5) architectures.
- **Large Language Model (LLM) Engineering:**
  - Prompt engineering patterns: Zero-shot, few-shot, Chain-of-Thought (CoT), ReAct.
  - Retrieval-Augmented Generation (RAG): Document chunking, vector embeddings, vector databases (ChromaDB, FAISS).
  - Parameter-Efficient Fine-Tuning (PEFT): LoRA, QLoRA using Hugging Face PEFT.
- **AI Agents:**
  - Autonomous loop patterns, tool and API integration, multi-agent frameworks (LangGraph, CrewAI).
- **Modules:** [`06-generative-ai`](../06-generative-ai/), [`07-ai-agents`](../07-ai-agents/)

---

## Phase 5: Production Deployment & MLOps (Weeks 21–24)
- **API Development:** Wrapping models inside asynchronous REST APIs with FastAPI.
- **Containerization:** Writing production `Dockerfile` configurations and multi-stage builds.
- **CI/CD:** Automated testing and linting pipelines with GitHub Actions.
- **Monitoring & Lifecycle:** Experiment tracking, model drift detection, reproducible pipelines.
- **Modules:** [`11-tools`](../11-tools/), [`Projects/advanced`](../../Projects/advanced)
