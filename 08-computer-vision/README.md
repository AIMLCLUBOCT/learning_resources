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
3. **Deep Learning for Vision & Real-Time Perception:**
   - Image classification: Pretrained architectures (ResNet, EfficientNet, Vision Transformers / ViT) using `torchvision.models`.
   - Real-time perceptual frameworks: Google **MediaPipe** for 21-point 3D hand tracking, 33-point body pose estimation, and 468-point facial mesh.
   - Robustness and failure boundaries: Benchmarking vision models under partial occlusion, illumination variance, and scale jitter.
4. **Object Detection & Localization:**
   - Bounding boxes: `[x_min, y_min, x_max, y_max]` vs `[center_x, center_y, width, height]`.
   - Intersection over Union (IoU) and Non-Maximum Suppression (NMS).
   - Modern real-time object detection: YOLO (You Only Look Once).
5. **Image Segmentation:**
   - Semantic segmentation (U-Net) vs. Instance segmentation (Mask R-CNN).

---

## 🗺️ Recommended Sequence

1. Work through the [OpenCV Python Tutorials](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html).
2. Explore [Google MediaPipe Python Quickstart](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker/python).
3. Follow the [Torchvision Transfer Learning Tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html).
4. Explore the [Ultralytics YOLO Documentation](https://docs.ultralytics.com/).
5. Build a real-time webcam detection or gesture recognition script.

---

## 💻 Practical Exercises

### Exercise 1: Real-Time Edge Detection with OpenCV
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

### Exercise 2: Hand Landmark Tracking with MediaPipe
```python
# pip install mediapipe opencv-python
import cv2
import mediapipe as mp

mp_hands = mp.solutions.hands
hands = mp_hands.Hands(
    static_image_mode=False,
    max_num_hands=1,
    min_detection_confidence=0.7
)

# Open webcam capture
cap = cv2.VideoCapture(0)
print("Press 'q' in the OpenCV window to exit...")

while cap.isOpened():
    ret, frame = cap.read()
    if not ret:
        break

    # MediaPipe requires RGB images; OpenCV defaults to BGR
    rgb_frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    results = hands.process(rgb_frame)

    if results.multi_hand_landmarks:
        for hand_landmarks in results.multi_hand_landmarks:
            # Landmark 8 is the index fingertip, Landmark 4 is thumb tip
            wrist = hand_landmarks.landmark[0]
            index_tip = hand_landmarks.landmark[8]
            h, w, _ = frame.shape
            cx, cy = int(index_tip.x * w), int(index_tip.y * h)
            cv2.circle(frame, (cx, cy), 10, (0, 255, 0), cv2.FILLED)

    cv2.imshow("Hand Landmark Tracking - AIML Club OCT", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

## 💡 Project Ideas
- **Campus Smart Attendance System:** Real-time face recognition and attendance logging using OpenCV and deep embeddings.
- **PPE / Helmet Detection System:** Train a YOLO model to identify construction workers or two-wheeler riders wearing safety helmets on college premises (see [AIMLCLUBOCT/Projects/intermediate/safety-helmet-detector](https://github.com/AIMLCLUBOCT/Projects/tree/main/intermediate/safety-helmet-detector)).
- **Hand Gesture Interface with Occlusion Benchmarking:** Build a real-time gesture recognition controller that benchmarks landmark tracking stability under synthetic 0%–60% hand occlusion.
- **Lightweight Eye & Gaze Tracker:** Real-time pupil detection for driver fatigue or attentiveness monitoring using OpenCV facial geometry.

---

## 📖 Official Documentation & Resources
- 🌐 [Google MediaPipe Solutions Documentation](https://developers.google.com/mediapipe)
- 📖 [OpenCV Official Python Tutorials](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html)
- 📖 [PyTorch Torchvision Documentation](https://pytorch.org/vision/stable/index.html)
- 📖 [Ultralytics YOLO Documentation](https://docs.ultralytics.com/)
- 🎓 [Stanford CS231n: Deep Learning for Computer Vision](http://cs231n.stanford.edu/)
