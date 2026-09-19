# Module 09: Natural Language Processing (NLP)

> Enable computers to understand, interpret, and generate human language using statistical techniques, word embeddings, and deep Transformer models.

---

## 📋 Prerequisites
- Module 01 (Python strings & data structures).
- Module 05 (Deep Learning, PyTorch, Recurrent Networks).

---

## 🧠 Core Concepts

1. **Text Preprocessing Fundamentals:**
   - Text normalization: Lowercasing, punctuation stripping, stopword removal.
   - Stemming (Porter stemmer) vs. Lemmatization (WordNet).
   - Part-of-Speech (POS) tagging and Named Entity Recognition (NER).
2. **Text Representation & Vectorization:**
   - Bag-of-Words (BoW) and CountVectorizer.
   - Term Frequency-Inverse Document Frequency (TF-IDF).
   - Distributed representations: Word2Vec (Skip-Gram, CBOW), GloVe, FastText.
3. **Subword Tokenization Algorithms:**
   - Why subword tokenization solves the Out-of-Vocabulary (OOV) problem.
   - Byte-Pair Encoding (BPE), WordPiece (BERT), SentencePiece (T5, LLaMA).
4. **Pretrained Transformer Models in NLP:**
   - BERT (Bidirectional Encoder Representations from Transformers) for understanding.
   - RoBERTa, DeBERTa, DistilBERT.
   - Sequence Classification, Token Classification (NER), and Question Answering pipelines.

---

## 🗺️ Recommended Sequence

1. Read the [Hugging Face Transformers Pipeline Quickstart](https://huggingface.co/docs/transformers/quicktour).
2. Study the [Stanford CS224n Course Notes](https://web.stanford.edu/class/cs224n/).
3. Explore the [spaCy Usage Guide](https://spacy.io/usage).
4. Train a text classifier using Hugging Face `Trainer`.

---

## 💻 Practical Exercises

### Exercise: Sentiment Analysis with Hugging Face Pipelines
```python
from transformers import pipeline

# Load pre-trained sentiment classification pipeline
classifier = pipeline("sentiment-analysis")

sentences = [
    "AIML Club OCT workshops are exceptionally hands-on and inspiring!",
    "The code had several unresolved dependency bugs and failed to run."
]

results = classifier(sentences)
for text, res in zip(sentences, results):
    print(f"Text: {text}\nPrediction: {res['label']} (Confidence: {res['score']:.4f})\n")
```

---

## 💡 Project Ideas
- **Campus Feedback Sentiment Analyzer:** Classify student feedback submitted through `voice.aimlcluboct.in` into constructive categories with automated priority tagging.
- **Academic Paper Abstract Summarizer:** Fine-tune a BART or T5 model to generate concise 3-sentence summaries of ArXiv computer science papers.

---

## 📖 Official Documentation & Resources
- 📖 [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers)
- 📖 [spaCy Industrial-Strength NLP Documentation](https://spacy.io/usage)
- 🎓 [Stanford CS224n: Natural Language Processing with Deep Learning](https://web.stanford.edu/class/cs224n/)
- 📖 [Natural Language Toolkit (NLTK) Book](https://www.nltk.org/book/)
