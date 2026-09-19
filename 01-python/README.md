# Module 01: Python for AI & Numerical Computing

> Master the foundational language of Artificial Intelligence: Python 3, object-oriented principles, virtual environments, and high-performance array operations with NumPy.

---

## 📋 Prerequisites
- Basic computer literacy and logical thinking.
- No prior programming experience required.

---

## 🧠 Core Concepts

1. **Python Fundamentals:**
   - Variables, dynamic typing, primitive data types (int, float, str, bool).
   - Control flow: `if-elif-else`, `while`, and `for` loops.
   - Built-in data structures: Lists, Tuples, Sets, and Dictionaries.
   - Functions, `*args`, `**kwargs`, lambda expressions, and scope.
2. **Object-Oriented Programming (OOP) for ML:**
   - Classes, attributes, methods, `__init__`, and `__call__` (crucial for custom PyTorch modules).
   - Inheritance and polymorphism.
3. **Environment Management:**
   - Why virtual environments matter.
   - Using `python -m venv` to isolate dependencies.
   - Installing and freezing requirements (`pip install`, `pip freeze > requirements.txt`).
4. **Numerical Computing with NumPy:**
   - Multidimensional arrays (`ndarray`), shape, dimensions, and data types (`dtype`).
   - Slicing and fancy indexing.
   - Vectorization vs. slow Python loops.
   - Broadcasting rules.
   - Linear algebra functions (`np.dot`, `@`, `np.linalg.inv`, `np.linalg.eig`).

---

## 🗺️ Recommended Sequence

1. Read [The Python Tutorial](https://docs.python.org/3/tutorial/) (Chapters 1 to 5).
2. Set up a local virtual environment in VS Code.
3. Practice writing modular functions and custom classes.
4. Read the [NumPy Quickstart Tutorial](https://numpy.org/doc/stable/user/quickstart.html).
5. Complete the practical exercises below.

---

## 💻 Practical Exercises

### Exercise 1: Vectorized Euclidean Distance
Implement Euclidean distance between two vectors using NumPy without using any `for` loops:

```python
import numpy as np

def euclidean_distance(v1: np.ndarray, v2: np.ndarray) -> float:
    """Calculate Euclidean distance using vectorized NumPy operations."""
    diff = v1 - v2
    return np.sqrt(np.sum(diff ** 2))

# Test
a = np.array([1.0, 2.0, 3.0])
b = np.array([4.0, 6.0, 8.0])
print("Distance:", euclidean_distance(a, b))  # Expected ~6.403
```

### Exercise 2: Matrix Multiplication Benchmark
Benchmark the performance difference between a 3-loop native Python matrix multiplication vs. `np.dot` / `@` on two $200 \times 200$ matrices. Observe the $50\times - 100\times$ speedup from vectorization!

---

## 💡 Project Ideas
- **Statistical CLI Tool:** A command-line Python script that reads any CSV file, parses numbers, and computes mean, median, standard deviation, and IQR using NumPy.
- **Custom Array Class:** Build an educational mini-array class from scratch with basic element-wise addition, subtraction, and dot product.

---

## 📖 Official Documentation & Resources
- 📖 [Official Python 3 Documentation](https://docs.python.org/3/)
- 📖 [NumPy User Guide](https://numpy.org/doc/stable/user/)
- 🎓 [CS50’s Introduction to Programming with Python](https://cs50.harvard.edu/python/)
