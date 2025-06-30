---
layout: post
title: "Medical Imaging"
author: pritesh
categories: [Python, Medical Imaging]
image: assets/images/medical-imaging-header.jpg
tags: [sticky, featured]
---

# X-ray Body Part Classifier – Quick Demo using AI

### 🧩 Problem Statement

In hospitals, thousands of X-ray images are generated daily but many are:

- Unlabeled or misfiled
- Mixed in storage without body-part tags

This makes it hard for doctors and AI systems to automatically route or diagnose these images efficiently.

---

### ❓ Why Are We Solving This?

Automatically identifying **which body part** an X-ray image belongs to can:

- Help organize and sort large medical datasets
- Serve as a **preprocessing step** for disease detection models
- Reduce human effort in data labeling
- Allow smart routing of images to relevant specialists

---

### Approach

We are building a **lightweight AI model** that:

1. Takes any X-ray image as input
2. Predicts the body part shown (e.g., wrist, shoulder, humerus)
3. Displays the prediction in a simple UI

---

### Dataset

For this demo, we used a **subset of the MURA dataset** (Stanford):

- 7 body part classes: elbow, finger, forearm, hand, humerus, shoulder, wrist
- 200 images per class to keep training fast

Structure:

data/
└── train/
├── elbow/
├── hand/
├── shoulder/
└── ...

Public datasets:

- [MURA Dataset (Stanford)](https://stanfordmlgroup.github.io/competitions/mura/)
- [VinDr X-ray Dataset (Kaggle)](https://www.kaggle.com/datasets/vinbigdata/vindr-cxr)

---

### Tech Stack

| Component               | Tool                              |
| ----------------------- | --------------------------------- |
| Deep Learning Framework | **PyTorch**                       |
| Model                   | **Pretrained ResNet18**           |
| Frontend UI             | **Streamlit**                     |
| Image Processing        | **Pillow, TorchVision**           |
| Deployment              | Local browser via `streamlit run` |

---

### Working

1. Training a ResNet18 on your labeled X-ray images
2. Saving the model and class labels
3. Using Streamlit to create a web app:
   - Upload an X-ray image
   - View predicted body part and confidence scores

---

### Output

- `xray_bodypart_model.pth` – the trained model
- Live web app to classify uploaded X-rays by body part

---

![X-ray Classifier Demo](assets/images/medical-imaging-demo.png)
