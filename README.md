# 🖼 Faster R-CNN Object Detection with PyTorch

This repository demonstrates how to perform **object detection and localization** using the **Faster R-CNN** model from `torchvision`.  
It includes functions for making predictions, filtering results, and visualizing bounding boxes with labels and confidence scores.

---

## 📌 Features

- Load a **pre-trained Faster R-CNN ResNet-50 FPN** model from `torchvision`.
- Detect and localize objects in an image.
- Filter predictions by:
  - **Confidence score threshold**
  - **Specific object classes**
- Draw bounding boxes and labels on the image using OpenCV.
- Supports multiple objects per image.

---

## 📦 Requirements

Install dependencies before running the code:

```bash
pip install torch torchvision torchaudio
pip install matplotlib opencv-python pillow numpy
```

## 📂 Files & Functions
1. get_predictions
```python
def get_predictions(pred, threshold=0.8, objects=None)
```
- Converts model output into a human-readable format.
- Filters results by confidence score and optional object names.
- Returns a list of tuples:
```
(class_name, probability, [(x1, y1), (x2, y2)])
```
2. draw_box
```python
def draw_box(predicted_classes, image, rect_th=10, text_size=3, text_th=3)
```
- Draws bounding boxes and labels on the image.
- Uses OpenCV for drawing and Matplotlib for displaying.

## 🎯 Object Detection Workflow
1. Load the model
2. Load and transform the image
3. Make predictions
4. Filter and visualize

## ⚠️ Notes
- Lowering the threshold increases false positives.
- objects parameter can be a list of labels or None to include all.
- The input image tensor should have shape (3, H, W) and values in [0, 1].
