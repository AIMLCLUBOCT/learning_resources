# Module 05: Deep Learning & Neural Networks

> Build and train deep neural networks from the ground up using PyTorch.

---

## 📋 Prerequisites
- Module 01 (Python OOP & NumPy).
- Module 02 (Calculus, Gradients, Matrix Operations).
- Module 04 (Model evaluation & train/test splits).

---

## 🧠 Core Concepts

1. **Neural Network Fundamentals:**
   - The Artificial Neuron (Perceptron): Weights, bias, linear combination $z = Wx + b$.
   - Activation functions: Why non-linearity is required (ReLU, Leaky ReLU, Sigmoid, Softmax, GELU).
   - Multi-Layer Perceptrons (MLP) / Feedforward Networks.
   - Loss functions: Cross-Entropy Loss (classification), MSE Loss (regression).
2. **Optimization & Training Dynamics:**
   - The Backpropagation algorithm: Recursive chain rule computation of $\frac{\partial L}{\partial W}$.
   - Optimizers: Stochastic Gradient Descent (SGD), Momentum, RMSProp, Adam, AdamW.
   - Learning rate schedules and warmup strategies.
   - Regularization: Dropout, Batch Normalization, Weight Decay ($L_2$).
3. **Convolutional Neural Networks (CNNs) for Vision:**
   - Convolution operation, kernel filters, stride, and padding.
   - Max pooling and average pooling.
   - Classic architectures: AlexNet, VGG, ResNet (Residual connections / skip connections).
4. **Sequence Models (RNNs & LSTMs):**
   - Recurrent connections and hidden states $h_t$.
   - Vanishing and exploding gradient problems.
   - Long Short-Term Memory (LSTM) gates: Forget, Input, Output gates.
   - Gated Recurrent Units (GRU).
5. **Introduction to the Transformer Architecture:**
   - Limitations of recurrence.
   - Self-Attention mechanism: Query ($Q$), Key ($K$), Value ($V$).
   - $\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$.

---

## 🗺️ Recommended Sequence

1. Work through the [PyTorch 60-minute Blitz](https://pytorch.org/tutorials/beginner/deep_learning_60min_blitz.html).
2. Read the seminal paper: *Deep Residual Learning for Image Recognition* (He et al., 2015).
3. Follow the [DeepLearning.AI Deep Learning Specialization](https://www.deeplearning.ai/courses/deep-learning-specialization/).
4. Train an image classification model on CIFAR-10 in PyTorch.

---

## 💻 Practical Exercises

### Exercise: Minimal PyTorch Neural Network
```python
import torch
import torch.nn as nn
import torch.optim as optim

# 1. Define Model
class MLP(nn.Module):
    def __init__(self, input_dim: int, hidden_dim: int, num_classes: int):
        super().__init__()
        self.net = nn.Sequential(
            nn.Linear(input_dim, hidden_dim),
            nn.ReLU(),
            nn.Dropout(0.2),
            nn.Linear(hidden_dim, num_classes)
        )
        
    def forward(self, x: torch.Tensor) -> torch.Tensor:
        return self.net(x)

# 2. Instantiate and run dummy batch
model = MLP(input_dim=20, hidden_dim=64, num_classes=2)
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=1e-3)

# Dummy inputs and targets
inputs = torch.randn(32, 20)
labels = torch.randint(0, 2, (32,))

# Forward, backward, step
outputs = model(inputs)
loss = criterion(outputs, labels)
optimizer.zero_grad()
loss.backward()
optimizer.step()

print(f"Step 1 Loss: {loss.item():.4f}")
```

---

## 💡 Project Ideas
- **Image Classification on CIFAR-10:** Train a custom ResNet architecture from scratch and implement data augmentation using `torchvision.transforms`.
- **Sentiment Classification with LSTM:** Build a bidirectional LSTM in PyTorch to classify IMDB movie reviews.

---

## 📖 Official Documentation & Resources
- 📖 [PyTorch Official Tutorials](https://pytorch.org/tutorials/)
- 📖 [PyTorch Documentation](https://pytorch.org/docs/stable/)
- 🎓 [Stanford CS231n: Deep Learning for Computer Vision](http://cs231n.stanford.edu/)
- 🎓 [Fast.ai: Practical Deep Learning for Coders](https://course.fast.ai/)
