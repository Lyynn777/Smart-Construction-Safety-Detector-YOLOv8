# Smart Construction Safety Detector (YOLOv8)

## Overview

An AI-based safety gear detection system that uses **YOLOv8** to automatically identify **helmets** and **safety vests** on construction sites.
This project aims to enhance safety monitoring and compliance in **real-estate and infrastructure** environments — aligning with the goals of **SitePace.ai** in automating safety and quality workflows.

---

## Tech Stack

* **Programming Language:** Python
* **Framework:** [Ultralytics YOLOv8](https://docs.ultralytics.com)
* **Dataset:** [Roboflow – Safety Vest + Helmet](https://universe.roboflow.com/test1-ut0wa/safety-vest-safety-helmet)
* **Environment:** Google Colab (Tesla T4 GPU)
* **Exports:** PyTorch (`.pt`) and ONNX (`.onnx`)

---

## Model Performance

| Metric            | Helmet | Vest  | Overall   |
| :---------------- | :----- | :---- | :-------- |
| **Precision (P)** | 0.943  | 0.823 | 0.883     |
| **Recall (R)**    | 0.783  | 0.679 | 0.731     |
| **mAP@50**        | 0.841  | 0.777 | **0.809** |
| **mAP@50–95**     | 0.448  | 0.436 | **0.442** |

**Interpretation:**
The model achieves high helmet precision and strong vest detection performance, suitable for **real-time construction safety monitoring**.

---

## Training Details

```bash
# Clone Ultralytics and install dependencies
pip install ultralytics==8.3.30 roboflow opencv-python

# Train YOLOv8
yolo detect train data=data.yaml model=yolov8s.pt epochs=50 imgsz=640 batch=16

# Validate performance
yolo detect val data=data.yaml weights=runs/detect/ppe_yolov8s3/weights/best.pt

# Predict on new images
yolo detect predict source=sample.jpg weights=runs/detect/ppe_yolov8s3/weights/best.pt
```

---

## Key Learnings

* Implemented a complete **object detection pipeline** using YOLOv8.
* Understood **bounding boxes**, **IoU**, and **mAP metrics**.
* Exported model to **ONNX** format for deployment flexibility.
* Hands-on experience in **Computer Vision for safety compliance**.

---

## Project Structure

```
Smart-Construction-Safety-Detector-YOLOv8/
│
├── runs/detect/ppe_yolov8s3/
│   ├── weights/
│   │   ├── best.pt
│   │   ├── best.onnx
│   │   └── last.pt
│   ├── results.png
│   └── predict/
│       └── image.jpg
│
├── data.yaml
└── README.md
```

---

⭐ *If you like this project, don’t forget to star the repo!*
