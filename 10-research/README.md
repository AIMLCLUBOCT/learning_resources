# Module 10: AI Research, Papers & Reproducibility

> Learn how to navigate cutting-edge literature, dissect academic papers, reproduce empirical benchmarks, and practice rigorous scientific methodology.

---

## 📋 Prerequisites
- Module 04 (Classical Machine Learning).
- Module 05 (Deep Learning & Neural Networks).
- Module 06 (Transformers & GenAI).

---

## 🧠 Core Concepts

1. **The Academic AI Ecosystem:**
   - Pre-prints: [arXiv.org](https://arxiv.org/) (fastest distribution of new research).
   - Major Conferences: NeurIPS, ICML, ICLR (core ML); CVPR, ICCV, ECCV (vision); ACL, EMNLP, NAACL (NLP).
   - Peer-review process and OpenReview platform.
2. **Systematic Paper Reading (The 3-Pass Method):**
   - **Pass 1 (Birds-eye):** Title, abstract, figures, and conclusion. Identify category, context, correctness, and contributions.
   - **Pass 2 (Grasp contents):** Read details, analyze charts, scrutinize baselines. Highlight unexplained terms.
   - **Pass 3 (Deep dive & reconstruction):** Mentally re-implement the authors' logic from scratch. Identify hidden assumptions and potential failure cases.
3. **Scientific Reproducibility & Open Science:**
   - Deterministic execution: Setting global random seeds across Python, NumPy, and PyTorch.
   - Documenting exact hardware and compute budgets (GPU hours, FLOPS).
   - Public code repositories linked with [Papers With Code](https://paperswithcode.com/).
4. **Academic Integrity & Research Ethics:**
   - Accurate representation of findings: Never cherry-pick favorable runs while omitting failures.
   - Avoiding false claims: Distinguish clearly between experimental student prototypes and peer-reviewed state-of-the-art benchmarks.
   - Plagiarism prevention and rigorous citation of prior art.

---

## 🗺️ Recommended Sequence

1. Read Prof. S. Keshav’s guide: *How to Read a Paper* (ACM SIGCOMM).
2. Choose one seminal paper from the reading list below.
3. Prepare a 5-slide summary deck using the [Research Presentation Template](../../.github/templates/README_TEMPLATE.md).
4. Attempt an independent replication of a key experiment table on a small public dataset.

---

## 📜 Must-Read Seminal Papers

1. **Transformers:** *Attention Is All You Need* (Vaswani et al., 2017) — [arXiv:1706.03762](https://arxiv.org/abs/1706.03762)
2. **Deep Residual Learning:** *Deep Residual Learning for Image Recognition* (He et al., 2015) — [arXiv:1512.03385](https://arxiv.org/abs/1512.03385)
3. **Parameter-Efficient Tuning:** *LoRA: Low-Rank Adaptation of Large Language Models* (Hu et al., 2021) — [arXiv:2106.09685](https://arxiv.org/abs/2106.09685)
4. **Agentic Reasoning:** *ReAct: Synergizing Reasoning and Acting in Language Models* (Yao et al., 2022) — [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)

---

## 💻 Practical Exercises

### Exercise: Setting Deterministic Seeds in PyTorch
```python
import os
import random
import numpy as np
import torch

def set_seed(seed: int = 42):
    """Set seeds across all random number generators for reproducible experiments."""
    random.seed(seed)
    os.environ['PYTHONHASHSEED'] = str(seed)
    np.random.seed(seed)
    torch.manual_seed(seed)
    if torch.cuda.is_available():
        torch.cuda.manual_seed_all(seed)
        torch.backends.cudnn.deterministic = True
        torch.backends.cudnn.benchmark = False

set_seed(42)
print("Experiment seeds locked for reproducibility.")
```

---

## 📖 Official Documentation & Resources
- 🌐 [arXiv.org Computer Science Repository](https://arxiv.org/list/cs.AI/recent)
- 🌐 [Papers With Code](https://paperswithcode.com/)
- 🌐 [Connected Papers Citation Graphs](https://www.connectedpapers.com/)
- 📖 [Distill.pub: Visual Explanations of ML Research](https://distill.pub/)
