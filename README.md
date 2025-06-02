# Smart-Glasses-for-visually-impaired-individuals
A wearable assistive system for visually impaired users using Raspberry Pi. It includes Object Detection, Emotion Recognition, Text-to-Speech, and Currency Detection with real-time audio feedback. Features are accessed via hand gestures using MediaPipe. Object detection is offloaded to a Flask API for faster performance.


## Overview
This project presents a cost-effective, AI-powered wearable system designed to assist visually impaired individuals in understanding their environment through real-time audio feedback. Built using a Raspberry Pi Zero 2 W, the smart glasses feature gesture-based mode switching powered by MediaPipe and offload processing to a cloud-based Flask API hosted on Google Colab.

## Key Features
- Object Detection – Identifies and announces surrounding objects using YOLOv8
- Emotion Detection – Recognizes facial expressions (e.g., happy, sad, angry) using DeepFace
- Text-to-Speech (TTS) – Extracts and reads printed/handwritten text using Tesseract OCR + gTTS
- Currency Detection – Detects Indian currency denominations using a custom-trained YOLOv8 model
- Gesture-Based Control – Switch modes using hand gestures (fist, palm, two-finger)
- Bluetooth Audio Output – Provides speech feedback via wireless earphones
- Cloud Offloading – Uses Flask + ngrok + Google Colab to run heavy ML models remotely

## Tech Stack
| Component    | Technology                                      |
|--------------|-------------------------------------------------|
| Hardware     | Raspberry Pi Zero 2 W, Pi Camera, Bluetooth headset |
| Backend      | Flask, Google Colab, ngrok                      |
| ML Models    | YOLOv8 (Objects, Currency), DeepFace (Emotions), Tesseract OCR (Text) |
| Libraries    | OpenCV, gTTS, PyBluez, MediaPipe, NumPy, threading |
| Protocols    | Wi-Fi (Image transfer), Bluetooth (Audio output) |



