# 🚀 Beginner AI/ML Roadmap: From Zero to First Model

> Designed for 1st-year and 2nd-year engineering students starting with zero prior machine learning knowledge.

---

## 🎯 Goal
By the end of this 8-week structured roadmap, you will understand core AI terminology, write clean Python code, clean real-world datasets, and train/evaluate your first machine learning models.

---

## 🗓️ Weekly Progression

### Week 1: Development Environment & Version Control
- **Goal:** Set up a clean local programming workspace.
- **Key Concepts:**
  - Installing Python 3.10+ and VS Code.
  - Command-line basics (PowerShell or Bash navigation).
  - Version control with Git & GitHub (clone, branch, commit, push, PR).
  - Virtual environments (`python -m venv .venv`).
- **Hands-on Task:** Create a GitHub account, star the AIML Club OCT repositories, and run a "Hello World" Python script inside a virtual environment.
- **Module:** [01-python](../01-python/)

### Week 2: Python Fundamentals & Data Structures
- **Goal:** Master core Python programming.
- **Key Concepts:**
  - Variables, data types, string formatting.
  - Lists, tuples, dictionaries, and sets.
  - Loops, list comprehensions, functions, and modules.
  - Exception handling and reading/writing files.
- **Hands-on Task:** Write a script that loads a CSV file and calculates basic summary statistics without external libraries.
- **Module:** [01-python](../01-python/)

### Week 3: Numerical Python (NumPy) & Vectorization
- **Goal:** Replace slow Python loops with high-performance array operations.
- **Key Concepts:**
  - `numpy.ndarray`, shapes, dimensions, and slicing.
  - Vectorization and broadcasting rules.
  - Matrix multiplication (`@` / `np.dot`), transposes, aggregations.
- **Hands-on Task:** Implement matrix multiplication and Euclidean distance calculations purely using NumPy vectorization.
- **Module:** [01-python](../01-python/)

### Week 4: Essential Mathematics Intuition
- **Goal:** Understand the "why" behind machine learning algorithms.
- **Key Concepts:**
  - Linear Algebra: Vectors, dot products, matrices as transformations.
  - Calculus: What is a derivative? What is a gradient? (Direction of steepest ascent).
  - Probability & Statistics: Mean, median, variance, standard deviation, normal distribution.
- **Recommended Resource:** [3Blue1Brown: Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra)
- **Module:** [02-mathematics](../02-mathematics/)

### Week 5: Data Analysis & Visualization (Pandas & Seaborn)
- **Goal:** Explore and visualize real-world tabular data.
- **Key Concepts:**
  - Pandas `Series` and `DataFrame`.
  - Filtering rows, handling missing values (`dropna`, `fillna`), grouping (`groupby`).
  - Plotting with Matplotlib and Seaborn (histograms, scatter plots, correlation heatmaps).
- **Hands-on Task:** Perform an Exploratory Data Analysis (EDA) on the Titanic dataset or Iris dataset in a Jupyter Notebook.
- **Module:** [03-data-science](../03-data-science/)

### Week 6: Supervised Learning (Regression & Classification)
- **Goal:** Train and understand your first predictive models.
- **Key Concepts:**
  - What is Supervised Learning? Features ($X$) vs. Labels ($y$).
  - Train-Test Split (`train_test_split`).
  - Linear Regression (gradient descent, Mean Squared Error).
  - Logistic Regression & Decision Trees for classification.
  - Using `scikit-learn`.
- **Hands-on Task:** Build a house price prediction model using Linear Regression on a Kaggle dataset.
- **Module:** [04-machine-learning](../04-machine-learning/)

### Week 7: Model Evaluation & Hyperparameter Tuning
- **Goal:** Accurately measure model performance and avoid overfitting.
- **Key Concepts:**
  - Overfitting vs. Underfitting (bias-variance tradeoff).
  - Classification metrics: Precision, Recall, F1-Score, Confusion Matrix, ROC-AUC.
  - K-Fold Cross Validation.
  - Basic hyperparameter search (`GridSearchCV`).
- **Hands-on Task:** Compare a Decision Tree against a Random Forest on a binary classification problem.
- **Module:** [04-machine-learning](../04-machine-learning/)

### Week 8: Capstone Beginner Project & Submission
- **Goal:** Package and document an end-to-end beginner project.
- **Key Concepts:**
  - Organizing project files (`src/`, `data/`, `notebooks/`).
  - Documenting your work using the [Project Template](../../.github/templates/PROJECT_TEMPLATE.md).
  - Deploying a simple interactive demo using Streamlit.
- **Hands-on Task:** Submit your capstone project repository to [AIMLCLUBOCT/Projects](../../Projects).

---

## 🎯 Next Step
Once you complete this beginner track, proceed to the [**Comprehensive AI/ML Roadmap**](./ai-ml-roadmap.md) to explore Deep Learning, Computer Vision, NLP, and Generative AI!
