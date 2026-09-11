---
layout: page
title: AI-Powered Cocoa Disease Inspection Platform
description: Full-stack cocoa disease detection with YOLO, ONNX Runtime, responsive bounding boxes, and human validation.
img: assets/img/project_img/Cocoa_and_chocolate_black.jpg
importance: 1
category: work
github: https://github.com/SujitBhatta21/Cocoa-Disease-Inspection
tech:
  - react/react-original
  - typescript/typescript-original
  - python/python-original
  - fastapi/fastapi-original
  - postgresql/postgresql-original
  - docker/docker-original
  - azure/azure-original
---

An actively developed, full-stack computer vision platform for identifying diseases and conditions in cocoa plants from field images. The project turns a trained object-detection model into a practical inspection workflow spanning image upload, inference, interpretable results, human review, and persistent inspection records.

Rather than treating every AI result as automatically correct, the platform gives inspectors the context and controls needed to validate uncertain predictions. Their corrections are stored with the inspection data and can later support model evaluation and retraining.

---

## Key Features

- **AI-assisted inspection** - upload cocoa pod, leaf, or plant images through a mobile-friendly React interface
- **Object detection** - locate detected conditions with bounding boxes instead of returning only a whole-image classification
- **Interpretable results** - display predicted labels, confidence scores, and detected regions over the uploaded image
- **Human validation** - flag low-confidence predictions for review and allow inspectors to correct predicted labels
- **Persistent records** - store inspection results, image references, confidence values, correction status, and timestamps in PostgreSQL
- **Secure access** - authentication, protected application routes, OAuth2 bearer tokens, and Argon2 password hashing
- **Inspection management** - organisation/user relationships and an administrative review workflow
- **Feedback pipeline** - retain corrected results for future dataset export, evaluation, and model retraining

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/React-TypeScript-61DAFB?style=flat-square&logo=react&logoColor=white" alt="React and TypeScript"/>
  <img src="https://img.shields.io/badge/Tailwind_CSS-UI-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/>
  <img src="https://img.shields.io/badge/FastAPI-Python-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
  <img src="https://img.shields.io/badge/YOLO-Object_Detection-111F68?style=flat-square" alt="YOLO object detection"/>
  <img src="https://img.shields.io/badge/ONNX_Runtime-Inference-005CED?style=flat-square&logo=onnx&logoColor=white" alt="ONNX Runtime"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Docker-Containers-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Azure-Blob_Storage-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Azure Blob Storage architecture"/>
</p>

<div class="row mt-2">
  <div class="col-sm-4">
    <h3>Frontend</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Technology</th><th>Purpose</th></tr></thead>
      <tbody>
        <tr><td>React + TypeScript</td><td>Inspection interface</td></tr>
        <tr><td>Tailwind CSS</td><td>Responsive styling</td></tr>
        <tr><td>Canvas/overlay UI</td><td>Bounding boxes</td></tr>
      </tbody>
    </table>
  </div>
  <div class="col-sm-4">
    <h3>Backend & AI</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Technology</th><th>Purpose</th></tr></thead>
      <tbody>
        <tr><td>FastAPI + Pydantic</td><td>REST API</td></tr>
        <tr><td>YOLO + ONNX Runtime</td><td>Model inference</td></tr>
        <tr><td>SQLAlchemy</td><td>Data access</td></tr>
      </tbody>
    </table>
  </div>
  <div class="col-sm-4">
    <h3>Data & Infrastructure</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Technology</th><th>Purpose</th></tr></thead>
      <tbody>
        <tr><td>PostgreSQL</td><td>Inspection records</td></tr>
        <tr><td>Docker</td><td>Containerised services</td></tr>
        <tr><td>Azure Blob Storage</td><td>Planned image storage</td></tr>
      </tbody>
    </table>
  </div>
</div>

---

## Inference and Validation Flow

1. An inspector uploads a cocoa image from the React interface.
2. The FastAPI backend validates the image and passes it to ONNX Runtime.
3. The exported YOLO model returns labels, confidence scores, and bounding-box coordinates.
4. The API sends structured detections back to the frontend.
5. React overlays each detection on the displayed image.
6. The inspector accepts or corrects the result when human validation is required.
7. The inspection and correction metadata are stored in PostgreSQL.
8. Corrected records can later contribute to model evaluation and retraining datasets.

Exporting the trained YOLO model to `.onnx` separates inference from the original training environment. The FastAPI service can load and run the model through ONNX Runtime without depending on the training pipeline.

---

## Engineering Challenge: Responsive Bounding Boxes

The model returns coordinates for the image's original dimensions, while browsers resize that image to fit different screens. Rendering the raw coordinates caused bounding boxes to drift away from the detected regions.

The interface calculates separate scale factors for the displayed image:

```text
scaleX = renderedWidth / naturalWidth
scaleY = renderedHeight / naturalHeight
```

It transforms each model coordinate with the matching scale factor before drawing the overlay. This keeps detections aligned as the image resizes across desktop and mobile layouts.

---

## Human-in-the-Loop Design

Predictions below the configured confidence threshold can require inspector validation. A reviewer can replace the predicted label, and the inspection record stores whether a correction was made and what the corrected label is.

This workflow makes model uncertainty visible and creates a structured feedback mechanism. Real-world corrections can be reviewed and exported as labelled examples for future evaluation and retraining instead of being lost after each inspection.

---

## Data Model

The backend models organisations, users, and inspections. Each inspection can record the responsible user, image reference, AI prediction, confidence score, human-correction status, corrected label, and creation timestamp.

---

## Project Status

The platform is near completion and remains under active development. The core application is designed around React and TypeScript, FastAPI, ONNX Runtime inference, PostgreSQL persistence, authentication, and a human-review workflow. Azure Blob Storage and dataset export form part of the evolving storage and model-improvement architecture.
