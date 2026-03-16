# Deepfake Detection Project Documentation 🧠🔍

Welcome to the **Deepfake Detection System**! This document serves as a high-level guide for the project's architecture.

> **🌟 STUDENT STUDY GUIDE**: If you are a student or a beginner, please read the [**PROJECT_STUDY_GUIDE.md**](./PROJECT_STUDY_GUIDE.md) first! It contains simplified explanations for every file and folder in the project.

---

## 📂 Project Structure Overview

The project is built using the **Django Web Framework** and **PyTorch** for the AI backend. Below is the complete directory structure and the role of each file.

### 1. Root Directory Files
- **`manage.py`**: The command-line utility for Django tasks (starting the server, migrations, etc.).
- **`requirements.txt`**: Lists all Python dependencies (Django, Torch, OpenCV, etc.) required to run the project.
- **`db.sqlite3`**: The local database used by Django to store session data and application state.
- **`.gitignore`**: Tells Git which files/folders to ignore (like `venv/`, `models/`, and `uploaded_videos/`).
- **`README.md`**: Professional documentation for GitHub users.

---

### 2. `ml_app/` (The Core Application)
This folder contains the main logic for the Deepfake detection system.

- **`views.py`**: **The Heart of the Project.**
  - **`class Model(nn.Module)`**: Defines the Neural Network architecture. It uses a **ResNext50** backbone for feature extraction and an **LSTM** (Long Short-Term Memory) layer to analyze the temporal sequence of video frames.
  - **`class validation_dataset(Dataset)`**: Handles video loading, frame extraction, and face cropping using `face_recognition` library.
  - **`predict_page`**: The primary function that:
    1. Loads the uploaded video.
    2. Extracts frames and detects faces.
    3. Runs the AI model to calculate a "Real" or "Fake" probability.
    4. Generates visual results for the user.
  - **`index`**: Handles the home page and video file uploads.

- **`urls.py`**: Defines the web routes for the app (e.g., `/`, `/predict/`, `/about/`).
- **`forms.py`**: Contains `VideoUploadForm`, which validates that the user uploads a video and selects a valid sequence length.
- **`templates/`**: HTML files for the application.
  - `index.html`: The modern dashboard for uploading videos.
  - `predict.html`: The results page showing probability scores and AI diagnostics.

---

### 3. `project_settings/` (Configuration)
- **`settings.py`**: Global configuration for Django, including security keys, database settings, and static/media file paths.
- **`urls.py`**: The main routing file that connects the project to the `ml_app`.

---

### 4. `models/` (AI Weights)
This folder contains the pre-trained `.pt` (PyTorch) model files. 
- Different models are optimized for different **Sequence Lengths** (e.g., 20, 40, 60, or 100 frames).
- The system automatically selects the most accurate model based on the user's input.

---

### 5. `static/` & `templates/` (Frontend & UI)
- **`static/js/face-api.js`**: Used for real-time face tracking and drawing "HUD" overlays on the video player in the browser.
- **`templates/base.html`**: The master layout providing the "Cyber-Forensics" dark theme, grid backgrounds, and navigation.
- **`templates/components/`**: Modular UI elements like `nn_animation.html` (the moving neural network background).

---

### 6. Media Folders (Generated Data)
- **`uploaded_videos/`**: Temporarily stores videos uploaded by users for analysis.
- **`uploaded_images/`**: Stores frames extracted from the video for the "Detailed Findings" section.

---

## 🚀 How the Prediction Process Works (Step-by-Step)

1. **Ingestion**: The user uploads a video file via the **Home Page**.
2. **Preprocessing**: 
   - The system reads the video using **OpenCV**.
   - It selects a specific number of frames (Sequence Length).
   - The **Face Recognition** library identifies and crops the face from each frame.
3. **AI Inference**:
   - The cropped faces are converted into mathematical tensors.
   - The **ResNext50** model extracts visual features from each face.
   - The **LSTM** analyzes how these features change over time (detecting unnatural movements or "glitches").
4. **Classification**: The model outputs two scores. A Softmax function converts these into a percentage (e.g., 98% Fake).
5. **Visualization**: The frontend displays the final verdict with a professional dashboard, showing the user exactly where the AI detected potential manipulation.

---

## 🛠️ Technical Stack
- **Backend**: Django (Python)
- **AI Framework**: PyTorch
- **Computer Vision**: OpenCV, Face-Recognition, Dlib
- **Frontend**: Tailwind CSS, JavaScript (face-api.js)
- **Models**: ResNext50 + LSTM

---
*Created for education and forensic analysis. © 2026 DeepFake Detection Lab.*
