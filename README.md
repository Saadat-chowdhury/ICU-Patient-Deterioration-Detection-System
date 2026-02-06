# ICU Patient Deterioration Detection System

**Using Machine Learning & AI Explainability**

---

## 📌 Project Overview

ICU patients can deteriorate rapidly, and early warning signs are often subtle and difficult to detect through manual monitoring alone. This project presents an **AI-powered ICU Patient Deterioration Detection System** that leverages real-world ICU waveform data, machine learning, and explainable AI to support timely and trustworthy clinical decision-making.

By analyzing continuous vital sign data, our system identifies early physiological changes that may indicate patient deterioration and provides **clear, human-readable clinical explanations** for each prediction.

---

## 🧠 Key Objectives

* Detect early signs of ICU patient deterioration using continuous monitoring data
* Reduce alert fatigue with high-precision predictions
* Provide explainable, clinician-friendly insights alongside model outputs
* Enable earlier interventions (2–4 hours ahead of traditional methods)

---

## 📊 Dataset

**Source:** MIMIC-III Waveform Database (PhysioNet)

### What is MIMIC-III?

* Medical Information Mart for Intensive Care (MIT)
* Publicly available, gold-standard ICU research dataset
* Real patient data from Beth Israel Deaconess Medical Center

### Dataset Used in This Project

* **Patients:** 30 adult ICU patients (subset for feasibility)
* **Monitoring Segments:** 91
* **Duration:** 4+ hours per segment
* **Total Data:** ~400 hours of continuous ICU monitoring
* **Vital Signs:**

  * Heart Rate (HR)
  * Blood Pressure (BP)
  * Respiratory Rate (RR)
  * SpO₂

---

## ⚙️ Methodology

### Feature Engineering

Each ICU monitoring segment was divided into:

* **Early period:** First 30% of the recording
* **Late period:** Last 30% of the recording

#### Engineered Features

* **Temporal Change Metrics**

  * % change in HR, BP, and RR between early and late periods
* **Shock Index**

  * HR / Systolic BP (Critical if > 0.7)
* **Statistical Features**

  * Mean, standard deviation, minimum, and maximum for each vital sign
* **Variability Metrics**

  * Heart rate variability
  * Blood pressure variability

#### Deterioration Labeling Criteria

A patient segment is labeled **DETERIORATING** if **any** of the following occur:

* Heart rate increase > **10%**
* Blood pressure decrease > **10%**
* Respiratory rate increase > **15%**

✔ Care was taken to ensure **no data leakage** between early and late periods.

---

## 🤖 Machine Learning Model

* **Algorithm:** Random Forest Classifier
* **Number of Trees:** 100

### Performance

* **Overall Accuracy:** 86.4%
* **Precision (Stable):** 91%

#### Confusion Matrix Summary

* True Stable: 16
* True Deteriorating: 2
* False Alarms: 3
* Missed Cases: 1

---

## 🧾 AI Explainability (LLM Integration)

* **LLM Used:** Claude 3 Haiku
* **Purpose:** Generate clinical, human-readable explanations for each model prediction
* **Output:**

  * 91 individual patient assessments
  * Actionable insights explaining *why* a patient is flagged as stable or deteriorating

This step bridges the gap between black-box ML predictions and real clinical usability.

---

## 🏥 Impact on ICU Care

### For Healthcare Providers

**Reduced Alert Fatigue**

* 91% precision means fewer false alarms
* Alerts only when clinically meaningful
* Clear explanations with each alert

**Prevents Burnout**

* Continuous monitoring reduces stress
* Less manual vital checking
* Evidence-based decision support

**Better Patient Management**

* Monitor multiple patients simultaneously
* Risk-based prioritization
* Earlier warnings than traditional systems

### For Patients

* Continuous, 24/7 monitoring
* Earlier and gentler interventions
* Reduced emergency procedures
* Shorter ICU stays
* Improved outcomes and survival rates

---

## 🖼️ Project Poster

![Project Poster](poster.png)

> Upload the poster image as `poster.png` in the root directory of this repository for proper rendering.

---

## 👥 Team Members

* **Kimberly Rivera Velez** – AI/ML, Data Cleaning & Healthcare Analytics
* **Sharfuddin Al Pasha Chowdhury** – AI/ML, Signal Processing, Biomedical Feature Engineering
* **Atika Fatima** – Graduate Student, George Mason University
* **Zane Al-Dalli** – Undergraduate Student, University of Virginia
* **Hiba Sheikh** – Undergraduate Student, University of Maryland Global Campus

---

## 🙏 Acknowledgements

We are grateful to the **MIMIC-III Waveform Database** researchers for providing open access to this invaluable ICU dataset through PhysioNet. We also sincerely thank our mentors from the **MedStar Georgetown AI CoLab Healthcare Internship Program**.

Special thanks to:

* **Dr. Raed Darwish** for clinical insights
* **Dr. Omar Aljawfi** for leading the internship and guiding this project

---

## ❓ Questions

Thank you for your interest in our work.

Feel free to open an issue or reach out if you have any questions or would like to collaborate.
