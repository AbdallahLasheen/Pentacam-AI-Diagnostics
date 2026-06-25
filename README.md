

<div align="center">
  <h1>👁️🤖 CornOrb: AI-Powered Keratoconus Diagnostic Portal</h1>
  
  <p><b>An advanced clinical web application for the early detection and diagnosis of Keratoconus using Pentacam Corneal Topography.</b></p>

  [![Python](https://img.shields.io/badge/Python-3.9+-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
  [![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-red.svg?logo=pytorch&logoColor=white)](https://pytorch.org/)
  [![Flask](https://img.shields.io/badge/Flask-Backend-black.svg?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
  [![HuggingFace](https://img.shields.io/badge/Deployed_on-Hugging_Face-yellow.svg?logo=huggingface&logoColor=black)](https://huggingface.co/spaces/Abdallah-12/CornOrb-Keratoconus-AI)
</div>

---

## 📖 Overview

**CornOrb** is a hybrid artificial intelligence and computer vision system designed to assist ophthalmologists in diagnosing **Keratoconus**—a progressive eye disease. The system relies on **Pentacam composite maps** to analyze corneal health.

Instead of relying solely on a black-box AI model, CornOrb combines:
1. **Vision Transformer (ViT):** A deep learning model that visually inspects the topography maps.
2. **Clinical OCR Engine:** A computer vision pipeline that extracts critical numerical parameters directly from the scans and applies standard medical rule-based thresholds.

This dual-engine approach ensures maximum reliability, transparency, and clinical accuracy.

---

## ✨ Key Features

- 🧠 **Vision Transformer (ViT) Inference:** Utilizes a custom-trained `MultiMap_ViT_B16` PyTorch model to classify cases as Normal or Keratoconus with detailed confidence scores.
- 🔍 **Robust Clinical OCR Engine:** Automatically extracts essential patient parameters from blurry or varied clinical reports. Extracted metrics include:
  - `K1`, `K2`, `Km`, `Astigmatism`
  - `Pachymetry`, `AC Depth`
  - `Max Elevation (Front & Back)`
- ⚖️ **Rule-Based Medical Assessment:** Evaluates extracted metrics against established medical thresholds (e.g., K Max > 49D, Thinnest Pachymetry < 470µm) to provide a transparent secondary opinion.
- 📁 **Multi-Modal Uploads:** Seamlessly drag-and-drop:
  - 4 Individual Maps (Axial, Front Elevation, Back Elevation, Thickness)
  - Single Composite Pentacam Images
  - Raw PDF Export Reports
- 💻 **Dynamic UI/UX:** A responsive, dark-themed medical dashboard optimized for clinical environments.

---

## 🏗️ System Architecture

The project is built on a robust, multi-layered stack:

| Component | Technology Used | Description |
|-----------|----------------|-------------|
| **Frontend** | Vanilla JS, HTML5, CSS3 | Glassmorphic, dark-themed responsive dashboard for intuitive interactions. |
| **Backend** | Python, Flask | Handles API routing, file processing, and system orchestration. |
| **Deep Learning**| PyTorch, Vision Transformer | `ViT-B/16` model tailored for composite medical image classification. |
| **OCR Pipeline** | Tesseract-OCR, OpenCV, PyMuPDF | Image preprocessing, text extraction, and PDF handling. |
| **Deployment** | Docker, HuggingFace Spaces | Containerized for seamless deployment and cloud scaling. |

---

## 🩺 Medical Rules Defined

The clinical rule-based engine evaluates cases independent of the AI model based on the following standard parameters:

| Parameter | Normal | Suspicious | Keratoconus Sign |
|-----------|--------|------------|------------------|
| **K Max (Front)** | `< 48 D` | `48 - 49 D` | `> 49 D` |
| **Thinnest Pachymetry**| `> 500 µm`| `470 - 500 µm`| `< 470 µm` |
| **Max Elevation (Front)**| `< 15 µm` | `15 µm` | `> 15 µm` |
| **Max Elevation (Back)** | `< 20 µm` | `20 µm` | `> 20 µm` |

---

## 🚀 Getting Started

### Prerequisites
Before you begin, ensure you have the following installed:
- **Python 3.9+**
- **Tesseract-OCR:** Download and install from [here](https://github.com/UB-Mannheim/tesseract/wiki). 
  *(Make sure to add it to your system PATH, e.g., `C:\Program Files\Tesseract-OCR\tesseract.exe`).*

### Local Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/AbdallahLasheen/Pentacam-AI-Diagnostics.git
   cd Pentacam-AI-Diagnostics
   ```

2. **Install dependencies:**
   It is recommended to use a virtual environment.
   ```bash
   pip install -r requirements.txt
   ```

3. **Download Model Weights:**
   Place your pre-trained model weights file (`MultiMap_ViT_B16_best.pth`) in the root directory. 
   > ⚠️ **Note:** Weights are not included in the repository due to GitHub file size limitations (LFS).

### Running the Application

Start the Flask local development server:
```bash
python app.py
```
Then, open your web browser and navigate to: **`http://127.0.0.1:5000`**

---

## 🌍 Live Demo

The application is deployed and accessible online via Hugging Face Spaces.
**Try it here:** [CornOrb Keratoconus AI on HuggingFace](https://huggingface.co/spaces/Abdallah-12/CornOrb-Keratoconus-AI)

---

## 📄 License & Disclaimer

- **License:** This project is for educational and research purposes.
- **Disclaimer:** This tool is an AI assistant and does not replace professional medical diagnosis. Always consult a certified ophthalmologist for clinical decisions.

---
<div align="center">
  <i>Designed and Developed by Abdo & Team</i>
</div>
