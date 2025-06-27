---
layout: post
title: "Medical Imaging"
author: pritesh
categories: [Python, Medical Imaging]
image: assets/images/medical-imaging.jpg
tags: [featured]
---

# 🦴 X-ray Body Part Classifier – Quick Demo using AI

## 🧩 Problem Statement

In hospitals, thousands of X-ray images are generated daily, but many are:

- Unlabeled or misfiled
- Mixed in storage without body-part tags

This makes it hard for doctors and AI systems to automatically route or diagnose these images efficiently.

---

## ❓ Why Are We Solving This?

Automatically identifying **which body part** an X-ray image belongs to can:

- Help organize and sort large medical datasets
- Serve as a **preprocessing step** for disease detection models
- Reduce human effort in data labeling
- Allow smart routing of images to relevant specialists

---

## 🧠 Approach

We are building a **lightweight AI model** that:

1. Takes any X-ray image as input
2. Predicts the body part shown (e.g., chest, hand, knee)
3. Displays the prediction in a simple UI

---

## 🗃️ Dataset

For the demo testing, we use a **small custom sample dataset** containing:

- Chest X-rays
- Hand X-rays
- (You can add more like knee, pelvis, skull)

We structure the dataset as:
data/
train/
chest/
chest1.png
hand/
hand1.png

## Public datasets like:

- [MURA Dataset (Stanford)](https://stanfordmlgroup.github.io/competitions/mura/)
- [VinDr X-ray Dataset (Kaggle)](https://www.kaggle.com/datasets/vinbigdata/vindr-cxr)

---

## ⚙️ Tech Stack

| Component               | Tool                              |
| ----------------------- | --------------------------------- |
| Deep Learning Framework | **PyTorch**                       |
| Model                   | **Pretrained ResNet18**           |
| Frontend UI             | **Streamlit**                     |
| Image Processing        | **Pillow, TorchVision**           |
| Deployment              | Local browser via `streamlit run` |

---

## 🚀 How It Works

1. Train a simple ResNet18 on your labeled X-ray images
2. Save the model and class labels
3. Use Streamlit to build a web interface:
   - Upload an image
   - View predicted body part + confidence score

---

## ✅ Output

- A trained model file: `xray_bodypart_model.pth`
- A live web app that classifies uploaded X-ray images by body part

---

## 📦 How to Run (Quick Start)

```bash
# Install dependencies
pip install torch torchvision streamlit pillow

# Train the model
python train.py

# Run the UI
streamlit run app.py
```
