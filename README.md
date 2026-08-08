# AI Deepfake Video Detection

An AI-powered deepfake video detection system designed to identify manipulated and AI-generated videos using a hybrid spatial-temporal deep learning approach.

## 📌 Overview

The rapid development of Generative AI, GANs, diffusion models, and neural rendering has made it increasingly difficult to distinguish real videos from manipulated content.

This project presents an automated Deepfake Video Detection pipeline that analyzes both:

- Spatial visual artifacts
- Frequency-domain abnormalities
- Temporal inconsistencies across video frames

The system classifies videos as **Real** or **Fake** and is designed with real-world video compression and deployment scenarios in mind.

## 🎯 Objectives

The main objectives of this project are:

- Detect AI-generated and manipulated videos automatically.
- Extract facial regions from video frames.
- Identify spatial artifacts using deep learning models.
- Analyze high-frequency manipulation patterns using FFT/DCT.
- Detect temporal inconsistencies using LSTM and 3D-CNN models.
- Improve robustness against H.264/H.265 video compression.
- Evaluate the system using Accuracy, AUC-ROC, F1-Score and EER.
- Explore real-time inference and production deployment.

## 🧠 System Architecture

The proposed system consists of multiple processing stages:

```text
Input Video
     │
     ▼
Video Frame Extraction
     │
     ▼
Face Detection & ROI Extraction
     │
     ├───────────────┐
     ▼               ▼
Spatial Branch    Frequency Branch
     │               │
 CNN / ViT         FFT / DCT
     │               │
     └───────┬───────┘
             ▼
      Feature Fusion
             │
             ▼
    Temporal Analysis
      │              │
    Bi-LSTM        3D-CNN
      │              │
      └──────┬───────┘
             ▼
      Classification
             │
       ┌─────┴─────┐
       ▼           ▼
     REAL         FAKE
