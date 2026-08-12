# Crop and Weed Detection using YOLOv8

**Machine Learning Internship Project – UCT / Upskill**

---

## 📌 Project Overview

This project focuses on detecting **crops** and **weeds** in agricultural field images using deep learning-based object detection. The goal is to enable precision spraying of pesticides only on weeds, reducing chemical usage and improving crop yield.

We used the **YOLOv8** object detection model trained on a dataset of sesame crop and weed images.

---

## 🎯 Problem Statement

Weeds compete with crops for nutrients, water, and sunlight, leading to reduced agricultural productivity. Traditional methods involve spraying pesticides across the entire field, which:

- Wastes chemicals
- Increases cost for farmers
- Can leave harmful residues on crops

**Solution:** Build an object detection system that can accurately distinguish between crops and weeds so that pesticides can be applied only where needed.

---

## 🗂️ Dataset

- **Name:** Crop and Weed Detection Dataset
- **Total Images:** 1300
- **Image Size:** 512 × 512
- **Classes:** 
  - `crop`
  - `weed`
- **Annotation Format:** YOLO format (bounding boxes)
- **Split:** 80% Training / 20% Validation

---

## 🛠️ Tech Stack

- Python
- Ultralytics YOLOv8
- Google Colab (GPU)
- OpenCV
- PyTorch

---

## 🚀 Model Training

- **Model:** YOLOv8n (nano)
- **Image Size:** 512
- **Epochs:** 50
- **Batch Size:** 16
- **Optimizer:** Default (AdamW)
- **Pretrained Weights:** COCO

### Training Command
```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
model.train(
    data="data.yaml",
    epochs=50,
    imgsz=512,
    batch=16,
    name="crop_weed_yolov8"
)
