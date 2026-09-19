# Module 08: Computer Vision

> Teach machines to interpret visual worlds: From basic image processing with OpenCV to real-time object detection with YOLO and deep vision models.

---

## 📋 Prerequisites
- Module 01 (Python & NumPy array manipulations).
- Module 05 (Convolutional Neural Networks with PyTorch).

---

## 🧠 Core Concepts

1. **Digital Image Fundamentals:**
   - Color spaces: RGB, BGR (OpenCV default), Grayscale, HSV.
   - Images as 3D NumPy arrays (`H x W x C`).
   - Coordinate systems and pixel transformations.
2. **Classical Image Processing with OpenCV:**
   - Image filtering, Gaussian blur, morphological operations (dilation, erosion).
   - Edge detection: Sobel, Canny edge detector.
   - Contours and bounding boxes.
   - Thresholding (Otsu's binarization).
3. **Deep Learning for Vision:**
   - Image classification: Pretrained architectures (ResNet, EfficientNet, Vision Transformers / ViT) using `torchvision.models`.
   - Transfer learning and fine-tuning.
4. **Object Detection & Localization:**
   - Bounding boxes: `[x_min, y_min, x_max, y_max]` vs `[center_x, center_y, width, height]`.
   - Intersection over Union (IoU) and Non-Maximum Suppression (NMS).
   - Modern real-time object detection: YOLO (You Only Look Once).
5. **Image Segmentation:**
   - Semantic segmentation (U-Net) vs. Instance segmentation (Mask R-CNN).

---

## 🗺️ Recommended Sequence

1. Work through the [OpenCV Python Tutorials](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html).
2. Follow the [Torchvision Transfer Learning Tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html).
3. Explore the [Ultralytics YOLO Documentation](https://docs.ultralytics.com/).
4. Build a real-time webcam detection script.

---

## 💻 Practical Exercises

### Exercise: Real-Time Edge Detection with OpenCV
```python
import cv2
import numpy as np

# Create a synthetic image with a white square
img = np.zeros((300, 300), dtype=np.uint8)
cv2.rectangle(img, (50, 50), (250, 250), 255, -1)

# Apply Canny Edge Detection
edges = cv2.Canny(img, threshold1=100, threshold2=200)

print("Original shape:", img.shape)
print("Detected edge pixels:", np.count_nonzero(edges))
```

---

## 💡 Project Ideas
- **Campus Smart Attendance System:** Real-time face recognition and attendance logging using OpenCV and deep embeddings.
- **PPE / Helmet Detection System:** Train a YOLO model to identify construction workers or two-wheeler riders wearing safety helmets on college premises.

---

## 📖 Official Documentation & Resources
- 📖 [OpenCV Official Python Tutorials](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html)
- 📖 [PyTorch Torchvision Documentation](https://pytorch.org/vision/stable/index.html)
- 📖 [Ultralytics YOLO Documentation](https://docs.ultralytics.com/)
- 🎓 [Stanford CS231n: Deep Learning for Computer Vision](http://cs231n.stanford.edu/)
