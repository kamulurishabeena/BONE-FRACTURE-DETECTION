# 🦴 FractureAI
### Hierarchical Deep Learning Framework for Bone Fracture Detection from X-ray Images

---

## 📌 Overview

**FractureAI** is a hierarchical deep learning system designed to detect bone fractures from musculoskeletal X-ray images.

Built using the **MURA (Musculoskeletal Radiographs) dataset**, the system uses EfficientNet-based transfer learning, Explainable AI (Grad-CAM + ROI), and a Flask web application to generate AI-assisted radiology reports in PDF format.

The project combines deep learning, explainable AI, and web deployment into an integrated medical imaging application.

## 🚀 Key Features

- 🔍 Anatomical region classification (Elbow, Hand, Shoulder)
- 🧠 Bone-specific fracture detection
- 📊 EfficientNetB1 transfer learning with ImageNet weights
- 📈 Model evaluation using standard classification metrics
- 🔎 Explainable AI using Grad-CAM
- 🎯 Region of Interest (ROI) extraction
- 📄 Automated PDF report generation
- 🌐 Flask-based web application
- ⚙️ Separate training and inference pipelines

## 🏗️ System Architecture

### Training Pipeline

1. MURA dataset collection
2. Image preprocessing and resizing (224 × 224)
3. Train-validation-test split
4. Anatomical region classification
5. Conditional model routing
6. Bone-specific fracture detection
7. Model evaluation

### Deployment Pipeline

1. Upload X-ray image through the web application
2. Process image using Flask backend
3. Predict anatomical region
4. Perform fracture classification
5. Generate Grad-CAM and ROI visualizations
6. Generate downloadable PDF report

**Note:** Model training is performed offline. The deployed application uses pre-trained models for inference.

## 🧠 Model Architecture

| Component | Description |
|---|---|
| Backbone | EfficientNetB1 |
| Input Size | 224 × 224 RGB |
| Learning Strategy | Transfer Learning |
| Pre-trained Weights | ImageNet |
| Classification | Multi-class and Binary |
| Output | Fractured / Normal |

### Hierarchical Classification

**Stage 1 – Anatomical Classification**

Identifies the anatomical region of the uploaded X-ray:

- Elbow
- Hand
- Shoulder

**Stage 2 – Fracture Detection**

Routes the X-ray image to the corresponding bone-specific model to classify it as fractured or normal.

## 🔎 Explainable AI (XAI)

The system incorporates Explainable AI techniques to improve prediction interpretability.

- **Grad-CAM:** Highlights image regions that contribute to the model's prediction.
- **ROI Extraction:** Identifies relevant regions of interest in the X-ray image.

Visual explanations are displayed alongside predictions and included in the generated PDF reports.

## 📊 Model Evaluation

The models are evaluated independently for each anatomical region using:

- Accuracy
- Precision
- Recall
- F1-score
- Loss

## 📂 Project Structure

```text
FractureAI/
│
├── app.py
├── predictions.py
├── visual_explainability.py
├── requirements.txt
│
├── templates/
│   ├── index.html
│   ├── predict.html
│   ├── result.html
│   └── about-model.html
│
├── static/
│   └── style.css
│
├── models/
│   └── Trained models
│
└── notebooks/
    ├── EfficientNetB1_Final_Elbow.ipynb
    ├── EfficientNetB1_Final_Hand.ipynb
    ├── EfficientNetB1_Final_Shoulder.ipynb
    └── EfficientNetB1_Parts.ipynb
```

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Vinaykumar21798/bonescan-ai.git

cd bonescan-ai
```

### 2. Create a Virtual Environment

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS:**

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## ▶️ Run the Application

```bash
python app.py
```

Open the local URL displayed in your terminal to access the application.

## 📄 Application Output

The system provides:

- Fracture classification result
- Prediction confidence score
- Grad-CAM visualization
- ROI-based explanation
- Downloadable AI-assisted PDF report

## 🎯 Applications

- Medical imaging research
- Radiology workflow assistance
- Clinical decision support research
- Educational applications in medical AI

## 🔮 Future Enhancements

- DICOM image support
- Uncertainty quantification
- Model drift monitoring
- Hospital PACS integration
- Support for additional anatomical regions

## 🛠️ Technologies Used

- **Programming:** Python
- **Deep Learning:** TensorFlow, Keras
- **Architecture:** EfficientNetB1
- **Computer Vision:** OpenCV
- **Explainable AI:** Grad-CAM
- **Backend:** Flask
- **Frontend:** HTML, CSS
- **Dataset:** MURA

## ⭐ Acknowledgment

Dataset: [MURA – Musculoskeletal Radiographs](https://stanfordmlgroup.github.io/competitions/mura/)

## 📜 Disclaimer

This project is developed for research and educational purposes. Its predictions are not a substitute for professional medical diagnosis.
