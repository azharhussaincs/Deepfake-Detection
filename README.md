# DeepFake Detection: Advanced AI Forensic Laboratory

[![Python Version](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Django Version](https://img.shields.io/badge/django-5.0%2B-green)](https://www.djangoproject.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🔬 Overview
DeepFake Detection is a professional-grade, industrial-level "Cyber-Forensics" dashboard designed to identify and analyze manipulated video content. Leveraging state-of-the-art Deep Learning (DL) and Computer Vision (CV) techniques, the system provides a comprehensive diagnostic report, including authenticity scores and frame-by-frame analysis.

The platform features a modern, high-fidelity Dark Mode interface with glassmorphism effects and real-time "Neural Network" animations, offering a "Neural Forensic Lab" experience.

## 🚀 Key Features
- **Neural Ingest Engine**: Supports multiple video formats (MP4, AVI, MOV, MKV) with an industrial-style upload interface.
- **Deep Learning Analysis**: Utilizes pre-trained neural models to detect subtle facial manipulations.
- **Computer Vision HUD**: Interactive video player with "Tactical HUD" overlays showing face tracking and diagnostic labels in real-time.
- **Detailed Forensic Reports**: Provides a "Detailed Findings" summary, probability scores, and an analysis of individual frames.
- **Professional Dashboard**: Dark Mode theme with technical grid patterns, animated neural nodes, and system status indicators.

## 🛠️ Tech Stack
- **Backend**: Django (Python)
- **AI/ML Frameworks**: PyTorch, Torchvision
- **Computer Vision**: OpenCV, Face-Recognition (dlib)
- **Frontend**: Tailwind CSS, JavaScript (face-api.js), HTML5 Canvas
- **Environment**: CPU-optimized execution (No GPU required for inference)

## 🛠️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/azharhussaincs/Deepfake-Detection.git
cd Deepfake-Detection
```

### 2. Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
# Additional face_recognition models
pip install git+https://github.com/ageitgey/face_recognition_models.git
```

### 4. Database Migrations
```bash
python manage.py migrate
```

### 5. Run the Application
```bash
python manage.py runserver
```
Access the dashboard at `http://127.0.0.1:8000/`.

## 📂 Project Structure
- `ml_app/`: Main application logic, views, and AI processing.
- `models/`: (Ignored in Git) Directory for pre-trained AI models.
- `static/`: Global CSS/JS assets and technical HUD components.
- `templates/`: Professional frontend layout using Tailwind CSS.
- `uploaded_videos/`: (Ignored in Git) Temporary storage for ingested evidence.

## ⚖️ Disclaimer
This tool is designed for educational and forensic research purposes. The accuracy of the detection is dependent on the quality of the source material and the underlying pre-trained models.

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
