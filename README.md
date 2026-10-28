# Corn FAW Detector 🌽🪰

### A Mobile Computer Vision System for Fall Armyworm Damage Detection in Maize Leaves

**Corn FAW Detector** is a mobile machine learning and computer vision project developed as part of my Master's research at Makerere University. The project investigates the use of convolutional neural networks (CNNs) to detect Fall Armyworm (FAW) damage in maize leaves and deploys the selected model as an Android application for field-level testing.

The project combines **image dataset curation, transfer learning, CNN model comparison, model evaluation, TensorFlow Lite conversion, Android deployment, and field testing**.

> **Research context:** This project was developed to explore how lightweight computer vision models can support maize pest detection in practical agricultural settings, particularly where smartphone-based tools may provide a more accessible means of obtaining preliminary crop assessments.

---

## 🎯 Project Objectives

The research had four main objectives:

1. Curate and prepare a dataset of maize leaf images representing healthy leaves and leaves affected by Fall Armyworm.
2. Compare the performance of three pretrained CNN architectures:
   - VGG16
   - MobileNetV2
   - InceptionV3
3. Evaluate the models using accuracy, confusion matrices, and F1-score.
4. Deploy the selected model as an Android application and evaluate its performance using unseen field images.

---

## 📊 Dataset

The core research dataset contained **2,868 maize leaf images**:

| Class | Images |
| --- | ---: |
| Healthy | 1,469 |
| Fall Armyworm damaged | 1,399 |
| **Total** | **2,868** |

The dataset was organized into training, validation, and testing subsets using an approximately **80:10:10 split**.

The dataset preparation and model development were carried out using real-world maize leaf images, with the aim of evaluating the models beyond purely controlled image conditions.

---

## 🧠 Model Development

The project evaluated three pretrained CNN architectures using transfer learning:

- **VGG16**
- **MobileNetV2**
- **InceptionV3**

The models were adapted for binary classification of maize leaves as either:

- Healthy
- Fall Armyworm damaged

Training and evaluation were performed using Python-based machine learning workflows in Jupyter notebooks. The models were trained and evaluated over **80 epochs**.

### Model Comparison

| Model | Training Accuracy | Testing Accuracy | F1 Score |
| --- | ---: | ---: | ---: |
| VGG16 | 97.90% | 98.26% | 0.98 |
| **MobileNetV2** | **99.87%** | **99.65%** | **1.00** |
| InceptionV3 | 98.21% | 92.68% | 0.92 |

Based on the comparative evaluation, **MobileNetV2 was selected for mobile deployment** because it achieved the strongest results among the three evaluated architectures.

---

## 📱 Mobile Deployment

The selected MobileNetV2 model was converted from the trained TensorFlow/Keras model into **TensorFlow Lite (`.tflite`)** for mobile deployment.

The resulting model was integrated into an Android application developed using:

- **Java**
- **Android Studio**
- **TensorFlow Lite**
- **XML**

The application allows a user to:

1. Capture a maize leaf image using the phone camera, or
2. Select an existing image from the phone gallery.
3. Submit the image for classification.
4. View the resulting classification.

The deployment process was designed around the practical constraints of smartphone-based agricultural applications.

---

## 🔬 Additional Unknown-Image Training

Following the initial model comparison, the selected MobileNetV2 model was additionally retrained using a merged dataset containing the original training data and **7,858 unknown images obtained from Kaggle**.

This retraining produced a reported testing accuracy of **99.71%**.

This result belongs to the subsequent retraining/deployment stage and should therefore be distinguished from the **99.65% testing accuracy** reported in the original three-model comparison.

---

## 🌱 Field Testing

The Android application was subsequently evaluated using **unseen maize leaf images during one week of field testing**.

A total of **300 leaves** were assessed:

| Application Result | Number |
| --- | ---: |
| Healthy | 200 |
| Fall Armyworm | 60 |
| Unknown | 40 |
| **Total** | **300** |

Comparison with the observed condition of the leaves showed:

- Of the **200 leaves classified as Healthy**, 180 were actually healthy.
- **20 leaves affected by Fall Armyworm were classified as Healthy**.
- All **60 leaves classified as Fall Armyworm** matched the observed condition.
- During repeated testing of 100 leaves, **80 produced consistent predictions**.
- A separate set of **50 non-maize leaves** was classified as **Unknown**.

These field results provided an additional perspective on model behaviour outside the original test dataset and subsequently informed the retrospective AI governance and risk assessment documented in this repository.

---

## ⚠️ Limitations

The research identified several limitations:

- False negatives occurred during field testing, including FAW-affected leaves being classified as Healthy.
- Field conditions introduced variation related to **image angle, shadows, weather, and camera conditions**.
- Field testing was affected by the timing of the study, as many maize plants were already approaching harvesting and some leaves had dried.
- InceptionV3 showed greater evidence of overfitting compared with VGG16 and MobileNetV2.
- Model training was affected by computational and runtime constraints during the research process.
- The ability to classify the tested non-maize images as **Unknown** was demonstrated in the field evaluation. However, this should not be interpreted as evidence of general out-of-distribution (OOD) detection across arbitrary unseen inputs.

---

## 🚀 Future Research

The dissertation identified several directions for further development:

- Expand and diversify the training dataset.
- Annotate affected regions of maize leaves to help the model focus on damaged areas.
- Further tune model hyperparameters to reduce false negatives.
- Investigate additional CNN architectures and ensemble approaches.
- Explore hybrid approaches combining deep learning with traditional image-processing techniques.
- Expand the system to support a broader range of agricultural crops and conditions.
- Conduct additional field evaluation during the active crop-growing period.

---

## 🛠️ Technologies

### Machine Learning & Computer Vision

- Python
- TensorFlow / Keras
- CNNs
- Transfer Learning
- VGG16
- MobileNetV2
- InceptionV3
- TensorFlow Lite

### Android Development

- Java
- Android Studio
- XML

### Research & Development

- Jupyter Notebooks
- Image dataset curation
- Model evaluation
- Confusion matrices
- Field testing

### AI Governance & Responsible AI

- AI Risk Assessment
- Risk Treatment Planning
- AI Monitoring & Oversight
- Human Oversight
- Data & Model Governance
- AI Incident Management
- AI Change Management
- NIST AI Risk Management Framework (AI RMF)

---

## 📂 Project Structure

```text
📁 CornFAWDetector/
│
├── 📱 Android App
│   ├── MainActivity.java
│   └── model.tflite
│
├── 🧠 Model Training
│   ├── VGG16_MobilenetV2_EfficientNetV2B0.ipynb
│   └── maize_dataset/
│
├── 🛡️ governance/
│   ├── README.md
│   └── Corn_FAW_AI_Governance_Case_Study.pdf
│
└── README.md
```

*The structure above describes the intended organisation of the project; individual folders/files may differ in the current repository.*

---

## 📸 Screenshots

### 🔍 Classification Results

**1. Classified as: Unknown**

![Unknown](./Result%20Unknown.jpg)

**2. Classified as: Fall Armyworm**

![Fall Armyworm](./Result%20Fallarmyworm%20.jpg)

**3. Classified as: Healthy**

![Healthy](./Result%20Healthy.jpg)

### 📲 Application Interface

This UI illustrates the interaction flow of the Corn FAW Detector Android app:

- Image display panel for the leaf.
- Buttons to take a photo, pick from gallery, and predict damage.
- Classification result panel.

![Application UI](./Application%20UI.jpg)

---

## 📌 Research Contribution

This project demonstrates an end-to-end applied machine learning workflow:

**Agricultural problem → Image dataset → CNN model development → Model comparison → MobileNetV2 selection → TensorFlow Lite conversion → Android deployment → Field evaluation**

The work is particularly focused on the practical application of computer vision to an agricultural challenge in Uganda and demonstrates the process of taking an ML model from experimental development into a mobile prototype for field testing.

The subsequent governance assessment extends this lifecycle:

**Field evidence → AI risk identification → Risk assessment → Risk treatment → Monitoring & oversight → Governance decision**

---

## 🛡️ AI Governance & Responsible AI Assessment

Following completion of the original MSc research, I conducted a **retrospective AI risk and governance assessment** of the Corn FAW Detector to examine what governance controls would be required if the research prototype were transitioned into sustained real-world deployment.

The assessment extends the original technical work beyond model accuracy to consider:

- model reliability and false-negative risk;
- geographic and data generalisation;
- image quality and input variation;
- human oversight and automation bias;
- purpose limitation and foreseeable misuse;
- operational performance degradation;
- user understanding and competency;
- data and model governance;
- AI incident and change management; and
- model/application integrity.

### AI Risk Register

The retrospective assessment identified **11 AI risks**:

| Risk Area | Initial Rating |
| --- | --- |
| False-negative FAW classification | **High** |
| Geographic/data generalisation | **High** |
| Image quality/input variation | **High** |
| Human over-reliance/automation bias | **High** |
| Out-of-scope use | Moderate |
| Operational performance degradation | **High** |
| Insufficient user understanding | Moderate |
| Model overfitting/model selection | Moderate |
| Inadequate post-deployment governance | **High** |
| Data governance/dataset accountability | Moderate |
| AI model/application integrity | Moderate |

The highest-rated risk was **false-negative FAW classification**, informed by the field observation that 20 FAW-affected leaves were classified as Healthy.

### Governance Position

A central conclusion of the assessment is that the Corn FAW Detector should be treated as an:

> **AI-assisted decision-support system rather than an autonomous agricultural diagnostic authority.**

If transitioned into sustained operational deployment, the proposed governance approach includes:

- explicit human oversight;
- intended-use and purpose limitations;
- additional field validation;
- monitoring of false negatives and other key risk indicators;
- safe handling of uncertain inputs;
- AI incident management;
- dataset and model traceability;
- model/data/application change control;
- periodic risk reassessment; and
- documented authority to continue, restrict, or suspend deployment.

### NIST AI RMF Mapping

The assessment is structured using the **NIST AI Risk Management Framework (AI RMF)**:

| NIST AI RMF Function | Application to Corn FAW Detector |
| --- | --- |
| **GOVERN** | Accountability, oversight, incident management, change control, and governance evidence |
| **MAP** | Purpose, stakeholders, operating context, foreseeable misuse, and potential harms |
| **MEASURE** | Model and field evaluation, KRIs, regional performance, and control-effectiveness monitoring |
| **MANAGE** | Risk prioritisation, treatments, escalation, residual risk, and deployment decisions |

The resulting governance lifecycle is:

**Assess → Decide → Monitor → Learn → Reassess**

### Governance Portfolio Artifacts

📘 **[View the AI Governance Case Study](governance/README.md)**

📄 **[Download the Full AI Risk Assessment & Governance Plan](governance/Corn_FAW_AI_Governance_Case_Study.pdf)**

> **Governance note:** This is a retrospective assessment developed after the original MSc research. Proposed governance structures and controls should not be interpreted as controls that were necessarily implemented during the original research.

---

## 🎓 Research Context

This project formed part of my Master's research in **Technology Innovation & Industrial Development at Makerere University**.

The original research focused on the development and evaluation of a mobile machine-learning system for Fall Armyworm damage detection in maize leaves.

A subsequent **retrospective AI governance and responsible AI assessment** builds on the original research to examine model reliability, deployment risks, human oversight, data governance, monitoring, system integrity, and responsible deployment.

The governance assessment applies the **NIST AI Risk Management Framework (AI RMF)** and includes an AI Risk Register, Risk Treatment Plan, Monitoring & Oversight Plan, governance roles, incident and change-management processes, and data/model governance controls.

➡️ **[Explore the AI Governance Assessment](governance/README.md)**

---

## 👩🏽‍💻 Author

**Rebecca Ssesanga**

ML Engineer · AI Governance Researcher

Makerere University — MSc Technology Innovation & Industrial Development

📧 **[rebeccassesanga@gmail.com](mailto:rebeccassesanga@gmail.com)**

🔗 GitHub: https://github.com/rebecca-ssesanga

---

## ⚖️ Academic & Governance Disclaimer

This project was developed as part of a **Master's thesis at Makerere University** and is shared here for **academic, educational, research, and demonstration purposes**.

The reported technical results reflect the datasets, experimental conditions, and field-testing conditions described in the associated research. While the application demonstrated promising performance during testing, **continued field evaluation is recommended to assess consistency across varying agronomic, environmental, geographic, device, and imaging conditions**.

The **Corn FAW Detector should not be treated as a substitute for professional agricultural diagnosis, expert assessment, or pest-management advice**. Field testing and further validation should be conducted before considering the system for operational or broader agricultural use.

The AI governance assessment contained in the `governance/` directory is **retrospective**. Technical results attributed to the MSc project reflect the original research evidence. Governance risk scores, controls, monitoring mechanisms, accountability structures, and other recommendations were developed subsequently as part of an AI Governance portfolio assessment.

For reuse, adaptation, or other academic use of this work, please contact:

**Rebecca Ssesanga**

📧 **[rebeccassesanga@gmail.com](mailto:rebeccassesanga@gmail.com)**

---

## 📄 Research & Governance Documentation

For the full methodology, dataset preparation, model development and evaluation, Android deployment, field-testing procedure, limitations, conclusions, and recommendations, please refer to the associated **Master's dissertation**.

For the subsequent responsible AI analysis, risk register, risk treatments, monitoring framework, governance roles, and NIST AI RMF mapping, see:

📘 **[AI Governance Assessment](governance/README.md)**

📄 **[Full AI Risk Assessment & Governance Plan](governance/Corn_FAW_AI_Governance_Case_Study.pdf)**

This repository therefore documents both the original **technical ML lifecycle** and the subsequent **retrospective AI governance assessment** of the Corn FAW Detector.
