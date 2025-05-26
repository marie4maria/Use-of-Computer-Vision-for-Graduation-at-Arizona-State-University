# 🎓 ASU Graduation Computer Vision Solution

A Computer Vision project designed to streamline Arizona State University’s graduation ceremony experience by replacing **paper-based QR codes** with **real-time facial recognition technology**. The system ensures faster identification, accurate display of student data on the Jumbotron, and improved photo tagging — all while reducing logistical chaos.

---

## 🚀 Project Overview

Traditional paper QR codes used at ASU graduation are fragile, inefficient, and easy to lose — especially when students have no pockets in their gowns. Our solution uses **facial recognition** to automate and secure this identification process in real-time, minimizing errors and delays.

---

## 🎯 Objectives

- Replace paper QR codes with facial recognition for **real-time student identification**
- Automate **photo tagging** and **Jumbotron displays**
- Reduce **logistical errors**, delays, and manual overhead
- Ensure **data security**, **accuracy**, and **privacy compliance**

---

## 🔍 How It Works

### 📷 At Check-In
- Student photo is captured and linked to their record in a secure database.

### 📸 At Photo Stations
- Face is recognized in real-time using OpenCV and dlib.
- Photo is auto-tagged and matched to student data.

### 🎥 At Stage/Jumbotron
- Live camera feed detects and identifies students walking the stage.
- Details like name and degree appear instantly on the screen.

---

## 🧠 Model Architecture

| Component                    | Description |
|-----------------------------|-------------|
| **Face Detection**          | HOG (Histogram of Oriented Gradients) for efficient detection |
| **Feature Embedding**       | dlib’s pretrained model generates 128D face vectors |
| **Recognition Logic**       | Face distance + confidence scoring with real-time matching |
| **Display & Interface**     | Real-time name overlay with color-coded confidence (green/yellow/red) |

---

## 🖥️ Tech Stack

- **Programming:** Python
- **Libraries:** OpenCV, dlib, face_recognition
- **Deployment:** Amazon EC2
- **Virtualization:** Python `venv` environment
- **OS Compatibility:** Windows, macOS, Linux
- **Data Storage:** JSON-based profile mappings, local image directories

---

## 🧪 Validation Strategy

- Requires ≥2 photos from multiple angles per student
- Recognition only succeeds if 8/10 consecutive frame matches
- Handles jitter-based re-verification for robustness
- Achieves >97% accuracy under normal lighting, >80% in low-light

---

## 🛡️ Privacy & Risk Mitigation

| Risk                      | Mitigation |
|---------------------------|------------|
| **Privacy concerns**      | Consent forms, encryption, transparent data policies |
| **Model bias**            | Diverse training data, fairness audits |
| **Technical integration** | Standard APIs, close collaboration with ASU IT |
| **Spoofing/hacking**      | Anti-spoofing, secure database, regular audits |

---

## 👥 Contributors

- **Mary John** – Process design, stakeholder analysis, schema mapping  
- **Delna Sophia Dsouza** – Risks, limitations, E2E integration, presentation  
- **Tsai-Yun Hsieh** – System development, UI design, model evaluation  
- **Sarah Le** – Research, model ideation, presentation design

---

## 📈 Key Features

- ✅ Real-time name + confidence overlay
- ✅ Jumbotron integration with live video feed
- ✅ Reload facial encodings without restart
- ✅ Multi-face detection to handle group entry
- ✅ Color-coded recognition status
- ✅ Adjustable confidence threshold via UI

---

## 🔧 How to Run Locally

```bash
# Create a virtual environment
python -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate

# Install required libraries
pip install opencv-python dlib face_recognition

# Run the system
python run_recognition.py
