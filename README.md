 🦴 FractureAI
Hierarchical Deep Learning Framework for Bone Fracture Detection from X-ray Images
📌 Overview
FractureAI is a deployment-ready, hierarchical deep learning system designed to automatically detect bone fractures from musculoskeletal X-ray images.

Built using the MURA (Musculoskeletal Radiographs) dataset, the system leverages EfficientNetB1-based transfer learning, incorporates Explainable AI (Grad-CAM + ROI) for interpretability, and is deployed through a Flask web application capable of generating AI-assisted radiology reports in PDF format.

This project combines research-grade modeling with real-world deployment architecture.

🚀 Key Highlights
🔍 Multi-class anatomical region classification (Elbow, Hand, Shoulder)
🧠 Bone-specific fracture detection models
📊 EfficientNetB1 with transfer learning (ImageNet)
📈 Performance evaluation using standard classification metrics
🔎 Grad-CAM based visual explanations
📄 Automated AI-assisted PDF report generation
🌐 Flask-based web deployment
⚙️ Clear separation of training and inference pipelines
🏗️ System Architecture
🔹 Training / System Architecture
Dataset collection (MURA)
Image preprocessing (224×224 resizing, normalization)
Train–validation–test split
Multi-class anatomical classification
Conditional routing
Bone-specific fracture detection models
Model evaluation
🔹 Deployment Architecture
Web-based X-ray upload
Flask backend processing
Pre-trained model inference
Explainable AI visualization
PDF report generation
Training is performed offline. Deployment uses pre-trained models for inference only.

🧠 Model Design
Component	Description
Backbone	EfficientNetB1
Input Size	224 × 224 RGB
Strategy	Transfer Learning
Tasks	Multi-class + Binary classification
Output	Fractured / Normal
Hierarchical Classification Strategy
1️⃣ Stage 1: Identify anatomical region 2️⃣ Stage 2: Route image to bone-specific fracture model

This improves generalization and reduces inter-anatomy feature confusion.

🔎 Explainable AI (XAI)
To ensure clinical interpretability:

Grad-CAM highlights influential image regions
ROI extraction localizes relevant structural areas
Visual explanations are displayed alongside predictions and embedded in generated reports.

📊 Evaluation Metrics
Accuracy
Precision
Recall
F1-score
Loss
Metrics are computed separately for each anatomical region.

📂 Project Structure
FractureAI/
│
├── app.py                     # Flask application
├── predictions.py             # Inference engine
├── visual_explainability.py   # Grad-CAM + ROI logic
├── requirements.txt
│
├── templates/                 # HTML frontend
│   ├── index.html
│   ├── predict.html
│   ├── result.html
│   └── about-model.html
│
├── static/
│   └── style.css
│
├── models/                    # Trained EfficientNet models
│
└── notebooks/                 # Training notebooks
    ├── EfficientNetB1_Final_Elbow.ipynb
    ├── EfficientNetB1_Final_Hand.ipynb
    ├── EfficientNetB1_Final_Shoulder.ipynb
    └── EfficientNetB1_Parts.ipynb
⚙️ Installation
1. Clone the repository
git clone https://github.com/Vinaykumar21798/bonescan-ai.git
cd bonescan-ai
2. Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows
3. Install dependencies
pip install -r requirements.txt
▶️ Run the Application
python app.py
📄 Output
The system provides:

Fracture classification result
Confidence score
Visual explanation (Grad-CAM + ROI)
Downloadable AI-assisted radiology report (PDF)
🎯 Applications
Clinical decision support systems
Radiology workflow assistance
Medical AI research
Educational tools for medical imaging
🔮 Future Enhancements
DICOM support
Uncertainty quantification
Model monitoring for drift detection
Integration with hospital PACS systems
Expansion to additional anatomical regions
👨‍💻 Author
Developed as part of an AI/ML research project focused on building explainable and deployable medical imaging systems.

⭐ Acknowledgment
Dataset: MURA – Musculoskeletal Radiographs

📜 License
For research and educational purposes.

Releases
No releases published
Packages
No packages published
Contributors
1
 (1)
@Vinaykumar21798
Vinaykumar21798TapelaVinaykumar
Languages
Jupyter Notebook
95.6%
HTML
2.8%
