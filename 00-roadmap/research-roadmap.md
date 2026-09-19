# 🔬 AI Research & Paper Replication Roadmap

> A specialized roadmap for students interested in reading research papers, reproducing experimental benchmarks, and contributing to novel applied AI work.

---

## 🎯 Goal
To develop the analytical ability to read top-tier AI conference papers (NeurIPS, ICML, ICLR, CVPR, ACL), understand novel mathematical formulations, reproduce empirical benchmarks, and formulate rigorous research questions.

---

## 🧭 Four-Phase Research Journey

```
Phase 1: Literature Reading ──► Phase 2: Code Replication ──► Phase 3: Ablation Studies ──► Phase 4: Novel Experimentation
```

---

### Phase 1: Literature Reading & Analysis Techniques
- **How to Read a Paper:**
  - Follow the *Three-Pass Approach* (Prof. S. Keshav):
    1. First pass: Title, abstract, introduction, section headings, and conclusion (5–10 mins).
    2. Second pass: Figures, tables, core algorithm, and mathematical notation.
    3. Third pass: In-depth re-implementation mental walk-through and assumptions check.
- **Where to Find Papers:**
  - [arXiv.org (cs.AI / cs.LG / cs.CV / cs.CL)](https://arxiv.org/)
  - [Papers With Code](https://paperswithcode.com/)
  - Major conference proceedings: NeurIPS, ICML, ICLR, CVPR, ICCV, ACL, EMNLP.
- **Foundational Paper Reading List:**
  1. *Attention Is All You Need* (Vaswani et al., 2017) — Transformers
  2. *Deep Residual Learning for Image Recognition* (He et al., 2015) — ResNets
  3. *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding* (Devlin et al., 2018)
  4. *LoRA: Low-Rank Adaptation of Large Language Models* (Hu et al., 2021)
  5. *ReAct: Synergizing Reasoning and Acting in Language Models* (Yao et al., 2022)

---

### Phase 2: Scientific Reproducibility & Code Replication
- **Replication Standards:**
  - Fix all random seeds (`random.seed()`, `np.random.seed()`, `torch.manual_seed()`).
  - Isolate exact library dependencies in `requirements.txt` with locked version hashes.
  - Detail hardware environment (GPU model, VRAM, CUDA version).
- **Public Baseline Verification:**
  - Validate model results against official paper tables using standard benchmark metrics (e.g., Top-1 Accuracy, BLEU score, perplexity).
  - Open-source the replication repository with clear instructions.

---

### Phase 3: Ablation Studies & Benchmarking
- **Conducting Ablations:**
  - Isolate variables: What happens when you remove Layer Normalization? What is the impact of varying the learning rate schedule?
  - Test on diverse domain datasets beyond the original paper's target benchmark.
- **Statistical Significance:**
  - Run multiple seeded runs (at least 3 to 5 trials) and report mean $\pm$ standard deviation.
  - Use boxplots and confidence interval plots to present findings honestly.

---

### Phase 4: Formulating Novel Applied Research
- **Problem Identification:** Focus on real-world constraints (e.g., low-resource edge deployment, domain adaptation for Indian languages, medical imaging on noisy scans).
- **Experimental Rigor:** Clearly document negative results as well as positive improvements.
- **Ethics & Academic Honesty:** Never manipulate data, claim unproven breakthroughs, or copy text without citations.

---

## 📚 Recommended Modules
- [Module 10: AI Research & Papers](../10-research/)
- [Curated Research Resources](../resources.md#11-research-papers--reproducibility)
