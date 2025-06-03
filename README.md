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


## Standards Used

| Standard                 | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| Wi-Fi 802.11             | Used for transmitting data from the Raspberry Pi Zero 2 W to the cloud server and receiving results back. |
| CSI                      | Connects the camera module to the Raspberry Pi, enabling high-speed image capture. |
| USB                      | Used to power the Raspberry Pi.                                             |
| Bluetooth                | Transmits audio output wirelessly to earphones or speakers.                |
| Flask + ngrok            | Facilitates cloud communication between Raspberry Pi and remote server using REST APIs. |
| OpenCV                   | Used for image preprocessing and text recognition from images.             |
| gTTS, Gemini, TTS        | Provides multilingual text-to-speech conversion, both online and offline.  |
| Raspberry Pi Zero 2 W    | Serves as the main processing unit of the smart glasses, integrating all hardware and software components. |


## Implementation Results

| Module              | Test Scenario                                  | Accuracy / Performance              | Remarks                                      |
|---------------------|-----------------------------------------------|-------------------------------------|----------------------------------------------|
| Gesture Control     | Fist, Two-finger, Palm gestures               | ~95% detection accuracy             | MediaPipe, works reliably under good lighting |
| Object Detection    | Detecting people, obstacles, doors            | ~85–90% accuracy (YOLOv8n)          | ROI + filtering improves relevance            |
| Text-to-Speech (TTS)| Printed and handwritten text (Eng, Telugu)    | >90% for printed, ~80% for handwritten | gTTS + Gemini performed best               |
| Currency Detection  | ₹10, ₹20, ₹50, ₹100, ₹500, ₹2000 notes        | 93% average detection accuracy      | Fine-tuned YOLOv8 model used                 |
| Emotion Detection   | Happy, Sad, Neutral expressions               | ~88% accuracy                       | DeepFace model, effective on faces           |
| Audio Feedback      | Bluetooth output to earphones                | <1s response time                   | Clear and responsive speech playback         |


