# Module 06: Generative AI & Large Language Models (LLMs)

> Explore the frontier of modern AI: Transformer architectures, prompt engineering, Retrieval-Augmented Generation (RAG), vector databases, and fine-tuning with Hugging Face.

---

## 📋 Prerequisites
- Module 05 (Deep Learning, Neural Networks, PyTorch basics).
- Basic understanding of embeddings and tokenization.

---

## 🧠 Core Concepts

1. **The Transformer Revolution:**
   - Multi-head self-attention and positional encodings.
   - Autoregressive models (GPT series) vs. Autoencoding models (BERT) vs. Sequence-to-Sequence (T5).
   - Pre-training (causal language modeling on massive web text) vs. Post-training (SFT, RLHF, DPO).
2. **Prompt Engineering Patterns:**
   - System prompts, user instructions, few-shot in-context learning.
   - Chain-of-Thought (CoT) reasoning.
   - Structured JSON outputs and schemas.
3. **Retrieval-Augmented Generation (RAG):**
   - The hallucination problem in LLMs.
   - Chunking strategies: Fixed size, semantic chunking, recursive character splitting.
   - Dense vector embeddings (e.g., `text-embedding-3-small`, BGE, MiniLM).
   - Vector Databases: ChromaDB, FAISS, Pinecone, Qdrant.
   - Similarity search: Cosine similarity and Approximate Nearest Neighbors (ANN).
4. **Parameter-Efficient Fine-Tuning (PEFT):**
   - Why full fine-tuning is computationally prohibitive.
   - Low-Rank Adaptation (LoRA) and Quantized LoRA (QLoRA).
   - Using Hugging Face `transformers`, `peft`, and `trl`.

---

## 🗺️ Recommended Sequence

1. Read [The Illustrated Transformer by Jay Alammar](https://jalammar.github.io/illustrated-transformer/).
2. Complete the free [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course).
3. Read the [DAIR.AI Prompt Engineering Guide](https://www.promptingguide.ai/).
4. Implement a local RAG pipeline over PDF documents using LangChain or LlamaIndex.

---

## 💻 Practical Exercises

### Exercise: Minimal Local RAG Pipeline (Concept)
```python
# Conceptual flow using Hugging Face & ChromaDB
from langchain_community.document_loaders import TextLoader
from langchain_text_splitters import RecursiveCharacterTextSplitter
from langchain_community.vectorstores import Chroma
from langchain_community.embeddings import HuggingFaceEmbeddings

# 1. Chunk document
text = "AIML Club OCT is the official AI club of Oriental College of Technology, Bhopal. Tagline: Innovate. Implement. Inspire."
splitter = RecursiveCharacterTextSplitter(chunk_size=50, chunk_overlap=10)
docs = splitter.create_documents([text])

# 2. Embed and store in local ChromaDB
embeddings = HuggingFaceEmbeddings(model_name="all-MiniLM-L6-v2")
vector_db = Chroma.from_documents(docs, embeddings)

# 3. Retrieve relevant context
query = "What is the tagline of AIML Club OCT?"
results = vector_db.similarity_search(query, k=1)
print("Retrieved Context:", results[0].page_content)
```

---

## 💡 Project Ideas
- **Campus Knowledge Q&A Assistant:** A RAG system that indexes the college syllabus, academic calendar, and exam rules to answer student questions accurately.
- **AI Code Reviewer:** A Generative AI application that takes code diffs and outputs actionable refactoring suggestions and security warnings.

---

## 📖 Official Documentation & Resources
- 📖 [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers)
- 📖 [Hugging Face PEFT Documentation](https://huggingface.co/docs/peft)
- 🎓 [Hugging Face Free NLP Course](https://huggingface.co/learn/nlp-course)
- 🌐 [DAIR.AI Prompt Engineering Guide](https://www.promptingguide.ai/)
