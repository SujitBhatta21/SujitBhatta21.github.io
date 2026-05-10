---
layout: page
title: Age Group Detection
description: Compared HOG+LBP+SVM, HOG+MLP, and CNN ResNet18 for classifying facial images into four age groups.
img: assets/img/project_img/3.jpg
importance: 3
category: fun
github: https://github.com/SujitBhatta21/age-group-detection
tech:
  - python/python-original
  - pytorch/pytorch-original
  - pypi/pypi-original-wordmark
  - googlecolab/googlecolab-original
---

A Computer Vision coursework (IN3060/INM460) comparing three model architectures for classifying images into four age groups: **Child, Young, Middle-Aged, Senior**.

---

## Models Compared

| Model | Accuracy | Macro F1 | Size |
|---|---|---|---|
| HOG + LBP + SVM | 71% | 0.70 | 35.7 MB |
| HOG + MLP | 69% | 0.67 | 3.6 MB |
| CNN ResNet18 | **72%** | **0.70** | 42.7 MB |

**Best model:** ResNet18 with transfer learning. Selected over SVM (same accuracy) because its confusion matrix showed zero Child↔Senior misclassifications, demonstrating meaningful age-ordering rather than random error.

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/PyTorch-ResNet18-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch"/>
  <img src="https://img.shields.io/badge/scikit--learn-SVM/MLP-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn"/>
  <img src="https://img.shields.io/badge/Google_Colab-Notebook-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" alt="Colab"/>
</p>

---

## Key Highlights

- Implemented HOG (8 orientations, 16×16 cells) + LBP (radius=3) feature concatenation for classical models
- ResNet18 fine-tuned with differential learning rates per layer group (layer3: 1e-5, layer4: 1e-4, fc: 1e-3)
- All models struggled with Middle-Aged class due to visual ambiguity at age boundaries - a known limitation of the dataset (Young: 350, Middle-Aged: 200 samples)
- Hyperparameter search compared ResNet18 vs ResNet50, VGG, EfficientNet-B0, multiple optimisers and schedulers