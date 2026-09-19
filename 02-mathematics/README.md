# Module 02: Mathematics for Machine Learning

> The four mathematical pillars of AI: Linear Algebra, Multivariate Calculus, Probability, and Statistics.

---

## 📋 Prerequisites
- High school mathematics (basic algebra, coordinate geometry, basic differentiation).
- Module 01 (Python & NumPy).

---

## 🧠 Core Concepts

```
┌─────────────────────────────────────────────────────────────┐
│               Mathematics for Machine Learning               │
├──────────────┬──────────────────┬─────────────┬─────────────┤
│Linear Algebra│     Calculus     │ Probability │ Statistics  │
│ Vectors      │ Derivatives      │ Bayes' Rule │ Hypothesis  │
│ Matrices     │ Gradients        │ Bayes Nets  │ Distributions│
│ Eigenvalues  │ Chain Rule       │ Joint/Cond. │ Estimation  │
│ SVD / PCA    │ Gradient Descent │ Expectations│ Variance    │
└──────────────┴──────────────────┴─────────────┴─────────────┘
```

### 1. Linear Algebra
- Vectors, linear combinations, span, linear independence, and basis.
- Matrices as linear transformations (rotation, scaling, reflection).
- Matrix multiplication, determinants, inverses.
- Eigenvalues and Eigenvectors ($A v = \lambda v$).
- Singular Value Decomposition (SVD) and its connection to Principal Component Analysis (PCA).

### 2. Multivariate Calculus
- Derivatives as rates of change; tangent lines.
- Partial derivatives: $\frac{\partial f}{\partial x_i}$.
- The Gradient Vector ($\nabla f$): Points in the direction of greatest rate of increase.
- Chain Rule: The mathematical engine behind backpropagation in deep neural networks.
- Gradient Descent: $w_{t+1} = w_t - \alpha \nabla L(w_t)$.

### 3. Probability Theory
- Sample space, events, probability axioms.
- Conditional probability and Bayes' Theorem:
  $$P(A|B) = \frac{P(B|A) P(A)}{P(B)}$$
- Random variables: Discrete (Bernoulli, Binomial) vs. Continuous (Gaussian / Normal, Uniform).
- Expectation ($\mathbb{E}[X]$) and Variance ($\text{Var}(X)$).

### 4. Applied Statistics
- Descriptive statistics: Mean, median, mode, variance, standard deviation, interquartile range (IQR).
- Inferential statistics: Population vs. sample, Central Limit Theorem (CLT).
- Hypothesis testing: Null hypothesis ($H_0$), p-values, z-test, t-test, significance levels ($\alpha$).
- Maximum Likelihood Estimation (MLE).

---

## 🗺️ Recommended Sequence

1. Watch the [3Blue1Brown Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra) series.
2. Watch the [3Blue1Brown Essence of Calculus](https://www.3blue1brown.com/topics/calculus) series.
3. Read selected chapters from [Mathematics for Machine Learning](https://mml-book.github.io/) (Free PDF).
4. Code mathematical intuition using NumPy and plot functions with Matplotlib.

---

## 💻 Practical Exercises

### Exercise: Manual Gradient Descent in Python
Implement 1D Gradient Descent to minimize $f(x) = x^2 - 4x + 4$ (where analytical minimum is at $x=2$):

```python
import numpy as np

def f(x):
    return x**2 - 4*x + 4

def df(x):
    return 2*x - 4

# Gradient Descent Optimization
x = 10.0  # Initial guess
learning_rate = 0.1
iterations = 30

for step in range(iterations):
    grad = df(x)
    x = x - learning_rate * grad
    if step % 5 == 0:
        print(f"Step {step:02d}: x = {x:.4f}, f(x) = {f(x):.6f}")

print(f"Converged at x = {x:.4f} (True minimum: 2.0)")
```

---

## 💡 Project Ideas
- **PCA from Scratch:** Implement Principal Component Analysis using NumPy's `np.linalg.eig` without using scikit-learn.
- **Hypothesis Testing Script:** Write a tool that runs a two-sample t-test to determine if two feature distributions differ significantly.

---

## 📖 Official Documentation & Resources
- 📖 [Mathematics for Machine Learning Textbook](https://mml-book.github.io/)
- 🎥 [MIT 18.06 Linear Algebra — Prof. Gilbert Strang](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)
- 🎥 [Khan Academy: Multivariable Calculus](https://www.khanacademy.org/math/multivariable-calculus)
- 📊 [StatQuest: Statistics & Probability Fundamentals](https://statquest.org/)
