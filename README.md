# 🌽 Corn FAW Detector
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

## 📉 Limitations
- Extended training time and training interruptions.
- Occasional **false negatives**.
- **Overfitting** observed in the InceptionV3 model during experimentation.

## 💡 Recommendations
- Hyperparameter tuning to reduce overfitting.
- Integrate regularization techniques like dropout and batch normalization.
- Conduct further testing during all maize growth stages for better generalization.

## 🔮 Future Work
- Annotate FAW-affected regions in images to improve model localization.
- Expand dataset to include other crop types and pests.
- Explore **ensemble learning** or hybrid CNN models for higher accuracy.

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



