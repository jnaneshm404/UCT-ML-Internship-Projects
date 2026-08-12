# Project Report

## Crop and Weed Detection using YOLOv8

**Machine Learning Internship Project**  
**Company:** UCT (Upskill)  
**Intern:** Jnanesh M  
**Project Duration:** August 2026

---

## 1. Background of the Project

Agriculture is the backbone of many economies, especially in countries like India. One of the major challenges faced by farmers is the presence of weeds in crop fields. Weeds compete with crops for essential resources such as nutrients, water, sunlight, and space. This competition significantly reduces crop yield and quality.

Traditionally, farmers control weeds by spraying herbicides or pesticides across the entire field. While this method is effective, it has several drawbacks:

- Excessive use of chemicals
- Increased cost of cultivation
- Environmental pollution
- Possible chemical residue on the final crop

With the advancement of Artificial Intelligence and Computer Vision, it is now possible to build intelligent systems that can automatically detect and differentiate between crops and weeds. This enables **precision agriculture**, where pesticides are applied only on the weed areas, reducing chemical usage and improving efficiency.

This project was undertaken as part of the Machine Learning Internship at **UCT (Upskill)** to develop a deep learning-based object detection system for identifying crops and weeds in field images.

---

## 2. Problem Statement and Relevance

### Problem Statement
Develop an object detection model that can accurately detect and classify **crops** and **weeds** in agricultural images so that targeted pesticide spraying can be performed.

### Relevance
- Helps in reducing the unnecessary use of pesticides
- Lowers the cost of cultivation for farmers
- Minimizes environmental damage
- Supports the concept of precision farming
- Has direct industrial and social impact in the agriculture domain

The project is highly relevant to current industrial demands in Agri-Tech and Smart Farming solutions.

---

## 3. Dataset Description

- **Dataset Name:** Crop and Weed Detection Dataset
- **Total Images:** 1300
- **Image Resolution:** 512 × 512 pixels
- **Classes:**
  - Crop
  - Weed
- **Annotation Format:** YOLO format (normalized bounding boxes)
- **Data Split:**
  - Training: 80%
  - Validation: 20%

The dataset contains images of sesame crops along with different types of weeds under real field conditions.

---

## 4. Design / Approach

The solution was designed using a modern object detection pipeline:

1. **Data Preparation**
   - Organized images and labels into proper YOLO directory structure
   - Created `train` and `val` splits
   - Generated `data.yaml` configuration file

2. **Model Selection**
   - Selected **YOLOv8n** (Ultralytics) because of its good balance between speed and accuracy
   - Used transfer learning with pretrained COCO weights

3. **Training Strategy**
   - Trained the model on Google Colab using GPU
   - Used data augmentation provided by Ultralytics
   - Monitored performance using mAP, Precision, and Recall

4. **Evaluation**
   - Validated the model on the validation set
   - Generated confusion matrix, PR curve, and result plots
   - Performed inference on sample images

---

## 5. Implementation Details

### Tools and Technologies Used
- Programming Language: Python
- Framework: Ultralytics YOLOv8
- Platform: Google Colab (GPU)
- Libraries: PyTorch, OpenCV, Matplotlib

### Training Configuration
- Model: YOLOv8n
- Image Size: 512
- Epochs: 50
- Batch Size: 16
- Optimizer: AdamW (default)
- Early Stopping Patience: 15

### Training Code (Summary)
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
The best model weights were saved as best.pt.

---

## 6. Results

The trained YOLOv8 model was evaluated on the validation set. The model successfully learned to distinguish between crops and weeds.
Key Observations:

 - The model was able to detect both crop and weed instances with good confidence.
 - Bounding boxes were accurately placed around the objects.
 - Performance metrics such as mAP50, Precision, and Recall were recorded.
 - Confusion matrix and training curves were generated for analysis.

All result graphs and sample prediction images are stored in the results/ folder of the project repository.

---

## 7. Learnings

During this project, the following key learnings were gained:

- Understanding of object detection pipelines and YOLO architecture
- Importance of proper dataset organization and train-validation split
- Practical experience in training deep learning models on GPU using Google Colab
- How to evaluate object detection models using mAP, Precision, and Recall
- Handling real-world agricultural image data
- Best practices for organizing a professional GitHub repository for internship projects
- Writing a structured technical project report

This project significantly improved practical knowledge of Computer Vision and its application in agriculture.

---

## 8. Conclusion

The Crop and Weed Detection project successfully demonstrates the use of YOLOv8 for precision agriculture. The developed model can detect crops and weeds from field images, which can be further integrated into automated spraying systems.
This project fulfills the requirements of the Machine Learning Internship at UCT and provides a strong foundation for future work in Agri-Tech and Computer Vision applications.

---

## 9. Future Scope

- Train larger models (YOLOv8s / YOLOv8m) for better accuracy
- Collect more diverse real-field images
- Deploy the model on edge devices (Raspberry Pi / Jetson)
- Integrate with a spraying robot or drone system
- Extend the system to multiple crop types

---

Submitted as part of Machine Learning Internship  
Company: UCT (Upskill)  
Intern: Jnanesh M  

---
