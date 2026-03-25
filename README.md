# 🌽 Corn FAW Detector – Mobile Computer Vision System for Fall Armyworm Detection in Maize Leaves

### A Mobile, Machine Learning-Based Application for Fall Armyworm Pest Damage Detection in Maize Leaves

![Project Banner](https://user-images.githubusercontent.com/placeholder/banner.png) <!-- Optional: Replace with a real banner image -->

## 📱 Overview
**Corn FAW Detector** is a mobile application developed as part of a Master's research project to tackle the critical issue of Fall Armyworm (FAW) infestations in maize crops. The app uses a lightweight, efficient deep learning model to detect FAW damage from maize leaf images, enabling faster, more accurate field-level pest diagnosis.

## 🧠 Problem Statement
- Early detection of FAW infestation is essential for effective pest management and crop health.
- Traditional inspection methods are slow, expensive, and prone to human error.
- There's a growing need for scalable, low-cost, tech-driven tools for real-time field diagnosis.

## 🎯 Objectives
- Curate a dataset of **2,868** maize leaf images (healthy vs FAW-damaged).
- Evaluate and compare CNN models including **VGG16**, **MobileNetV2**, and **InceptionV3**.
- Measure performance using the **F1 Score** from the confusion matrix.
- Deploy the best-performing model in an Android application for real-world use.

## 🔧 Methodology
- 📸 **Data Collection:** Sourced from an ongoing agricultural research project in Uganda.
- 🧹 **Preprocessing:** Image resizing, normalization, and augmentation.
- 🧪 **Model Training:** Used transfer learning on multiple CNN architectures.
- 📲 **Deployment:** Integrated the best model (MobileNetV2) using **TensorFlow Lite** into an Android app using Java.

## 🚀 Results
- **MobileNetV2** achieved:
  - 🟢 **Training Accuracy:** 99.87%
  - 🧪 **Test Accuracy:** 99.65%
  - 🏆 **F1 Score:** 1.00
- Real-world testing on 300 maize leaves showed robust accuracy and reliability under different conditions.

## 🧪 Field Testing
- Tested on diverse maize samples across varying lighting and weather conditions.
- Compatible with different Android cameras.
- Positive user feedback on usability and real-time prediction.

## Real-World Validation Results

| Category | Metric | Result | Analysis |
| :--- | :--- | :--- | :--- |
| **Detection** | Precision | 100% | No false alarms for Fall Armyworm damage. |
| **Sensitivity** | Healthy Recall | 90% | Successfully validated 180 out of 200 healthy samples. |
| **Structural** | OOD Detection | 100% | Properly rejected 50/50 non-maize crop images. |
| **Reliability** | Test-Retest | 80% | Consistent classification across repetitive field runs. |
| **UX/UI** | User Rating | High | Validated for speed, ease of use, and multi-device compatibility. |

---

## 🔍 Lessons Learned & Research Insights

This section highlights the critical insights gained during the development and field-testing of the MobileNetV2 model.

### 1. Error Analysis: Addressing False Negatives
The field test identified **20 instances** where diseased leaves were classified as "Healthy" (False Negatives). This indicates a specific **Recall gap** that is critical for early intervention in agricultural settings.
* **The Root Cause:** Preliminary analysis suggests these errors occurred during **early-stage infection** where lesions were small or partially obscured by shadows and leaf folds.
* **Engineering Fix:** I plan to implement **Heatmap Visualization (Grad-CAM)** to interpret the model's focus areas and refine feature extraction for subtle lesion patterns.

### 2. Environmental Sensitivity
While the application demonstrated high camera compatibility, performance fluctuated under **extreme sunlight angles**.
* **Research Insight:** Real-world agricultural data is significantly "noisier" than curated datasets. Harsh lighting and varied occlusion can degrade model generalization.
* **Future Mitigation:** I will expand the training pipeline with **advanced data augmentation**—specifically simulating diverse lighting and shadow conditions—to improve field robustness.

### 3. Structural Specificity vs. Generalization
The model successfully rejected **100% of non-maize crops** (Out-of-Distribution data).
* **Key Finding:** This confirms that the **MobileNetV2** architecture, combined with my custom dataset of 2,868 images, developed a strong feature extraction capability for **maize-specific morphology**.

---

## 📉 Limitations
- **Operational Constraints:** Extended training time and training interruptions due to resource limitations.
- **Model Reliability:** Occasional **false negatives** in early-stage pest detection.
- **Overfitting:** Observed in the **InceptionV3** model during the experimentation phase, leading to the selection of the more efficient MobileNetV2 for final deployment.

## 💡 Recommendations
- **Optimization:** Perform hyperparameter tuning and integrate regularization techniques like **Dropout** and **Batch Normalization** to further reduce overfitting.
- **Generalization:** Conduct additional testing across **all maize growth stages** to ensure the model handles variations in leaf size and color throughout the season.

## 🔮 Future Work
- **Model Interpretability:** Implement **Grad-CAM** to improve model localization and user trust.
- **Dataset Expansion:** Annotate FAW-affected regions in images and expand the dataset to include other pests and crop types.
- **Advanced Architectures:** Explore **Ensemble Learning** or hybrid CNN models to push accuracy beyond current benchmarks.

## 📂 Project Structure

```
📁 CornFAWDetector/
├── 📱 Android App (Java)
│   ├── MainActivity.java
│   ├── model.tflite (MobileNetV2)
├── 🧠 Model Training (Python)
│   ├── VGG16_MobilenetV2_EfficientNetV2B0.ipynb
│   └── maize_dataset/
```

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


## 🛠️ Tools & Technologies
- Android Studio (Java)
- TensorFlow & TensorFlow Lite
- Google Colab / Jupyter Notebook
- OpenCV & Matplotlib (for preprocessing & visualization)

## 👩‍💻 Author
**Rebecca Ssesanga**  
Master of Science in Technology Innovation and Industrial Development  
Makerere University, Uganda  
📧 nalybecks@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/rebecca-ssesanga-042935187)

## 📌 Academic Use Disclaimer

This project was developed as part of a Master's thesis at **Makerere University**.  
It is shared here for academic and demonstration purposes only.  
Please contact the author (**Rebecca Ssesanga**) at 📧 nalybecks@gmail.com for reuse permissions.

---

> ⚠️ *This project is research-based and intended for educational and agricultural extension purposes. Field testing should be continued to ensure consistent performance across varying agronomic conditions.*



