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

---

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
```

---

## 📊 Results
The model was evaluated on the validation set. Key metrics:

- mAP50
- mAP50-95
- Precision
- Recall

Detailed graphs (results.png, confusion matrix, PR curve) are available in the results/ folder.
Sample predictions are also included in the results/sample_predictions/ folder.

---

## 📁 Project Structure

01-Crop-Weed-Detection/  
├── README.md  
├── data.yaml  
├── notebooks/  
│   └── Crop_Weed_Detection_YOLOv8.ipynb  
├── models/  
│   └── best.pt  
├── results/  
│   ├── confusion_matrix.png  
│   ├── results.png  
│   └── sample_predictions/  
├── report/  
│   └── Project_Report_Crop_Weed_Detection.md  
└── src/  

---

## 💻 How to Run

Clone this repository
Install requirements: 
```bash
-pip install ultralytics
```
Update the path in data.yaml according to your system
Run inference:
```python
Pythonfrom ultralytics import YOLO
model = YOLO("models/best.pt")
model.predict("path/to/image.jpg", save=True)
```

---

##📝 Learnings

- Data preparation and YOLO format annotations
- Training object detection models using Ultralytics
- Evaluating model performance using mAP, Precision, and Recall
- Importance of train-validation split and data organization
- Working with Google Colab GPU for deep learning

---

##👨‍💻 Author  

Jnanesh M
Machine Learning Intern – UCT / Upskill

---

##📄 License  

This project was developed as part of the Machine Learning Internship at UCT.
