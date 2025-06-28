# Tomato-Leaf-Disease-Classification-with-Transfer-Learning-DenseNet121

## Business Understanding
Jaya Jaya Institut merupakan salah satu institusi pendidikan perguruan yang telah berdiri sejak tahun 2000. Hingga saat ini ia telah mencetak banyak lulusan dengan reputasi yang sangat baik.

## Project Overview

This project utilizes transfer learning with the **DenseNet121** architecture to classify different types of **tomato leaf diseases** from images. Early and accurate detection of plant diseases is essential for improving agricultural productivity and minimizing crop loss.

---

## Problem Statement

Tomato crops are vulnerable to various diseases that significantly impact yield and quality. Manual disease detection is time-consuming, error-prone, and requires expert knowledge. To solve this, we aim to build an intelligent, automated classification model to detect tomato leaf diseases based on image data.

---

## Project Objectives

- Build an image classification model using **DenseNet121** and **transfer learning**.
- Predict and identify tomato leaf diseases from uploaded images.
- Evaluate model performance using metrics such as **accuracy**, **precision**, **recall**, and **F1-score**.
- Deploy the model for interactive prediction and real-time use in platforms like **Colab** or **Streamlit**.

---

## Dataset

dataset : [tomatoleaf-dataset](https://www.kaggle.com/datasets/kaustubhb999/tomatoleaf)
The dataset consists of categorized images of tomato leaves infected with various diseases, including:

- Tomato___Bacterial_spot  
- Tomato___Early_blight  
- Tomato___Late_blight  
- Tomato___Leaf_Mold  
- Tomato___Septoria_leaf_spot  
- Tomato___Spider_mites  
- Tomato___Target_Spot  
- Tomato___Tomato_mosaic_virus  
- Tomato___Tomato_Yellow_Leaf_Curl_Virus  
- Tomato___healthy

### Setup Environment (Local Deployment)

Ikuti langkah-langkah berikut untuk menjalankan aplikasi secara lokal:

#### 1. Clone Repository
```bash
https://github.com/Matahari-Masalalu/Menyelesaikan-Permasalahan-Institusi-Pendidikan.git
cd /Menyelesaikan-Permasalahan-Institusi-Pendidikan
```

#### 2. Create a Virtual Environment
```bash
virtualenv venv
```

#### 3. Activate the Virtual Environment
Windows:
```bash
venv\Scripts\activate
```
macOS/Linux:
```bash
source venv/bin/activate
```

#### 4. Install Dependencies
```bash
pip install -r requirements.txt
```

#### 5. Jalankan Aplikasi Streamlit
```bash
streamlit run streamlit_app.py
```

---

## Model Architecture

- **Base Model**: DenseNet121 (pretrained on ImageNet)
- **Top Layers**:
  - `BatchNormalization`
  - `Dense(256, activation='relu')`
  - `Dropout(0.35)`
  - `Dense(120, activation='relu')`
  - `Dense(10, activation='softmax')` for classification

---

## Training Setup

- **Image Size**: 256x256
- **Loss Function**: Categorical Crossentropy
- **Optimizer**: Adam (learning rate = 0.0001)
- **Batch Size**: 32
- **Epochs**: 100 with EarlyStopping
- **Label Mode**: Categorical (One-hot)

---

## Evaluation Metrics
- **Accuracy**: 95%
- **Precision, Recall, F1-score** per class using `classification_report`
- **Confusion Matrix** for visual class prediction performance

![image](https://github.com/user-attachments/assets/990e3ca7-2f00-4128-8d0f-c45f66631b42)

| Class                                             | Precision | Recall | F1-Score | Support |
|--------------------------------------------------|-----------|--------|----------|---------|
| Tomato___Bacterial_spot                          | 0.961     | 0.990  | 0.975    | 100     |
| Tomato___Early_blight                            | 0.946     | 0.870  | 0.906    | 100     |
| Tomato___Late_blight                             | 0.889     | 0.960  | 0.923    | 100     |
| Tomato___Leaf_Mold                               | 0.935     | 0.870  | 0.902    | 100     |
| Tomato___Septoria_leaf_spot                      | 0.876     | 0.920  | 0.898    | 100     |
| Tomato___Spider_mites Two-spotted_spider_mite    | 0.919     | 0.910  | 0.915    | 100     |
| Tomato___Target_Spot                             | 0.922     | 0.830  | 0.874    | 100     |
| Tomato___Tomato_Yellow_Leaf_Curl_Virus           | 0.970     | 0.980  | 0.975    | 100     |
| Tomato___Tomato_mosaic_virus                     | 0.952     | 1.000  | 0.976    | 100     |
| Tomato___healthy                                 | 0.962     | 1.000  | 0.980    | 100     |
| **Accuracy**                                     | **0.933** | **0.933** | **0.933** | **1000** |
| **Macro Average**                                | 0.933     | 0.933  | 0.932    | 1000    |
| **Weighted Average**                             | 0.933     | 0.933  | 0.932    | 1000    |


## Kesimpulan
Berdasarkan analisis dan pemodelan yang dilakukan, ditemukan beberapa insight penting:
- Mahasiswa yang tidak membayar tepat waktu, tidak menerima beasiswa, dan memiliki tunggakan cenderung memiliki kemungkinan lebih tinggi untuk dropout.
- Jurusan tertentu seperti Veterinary Nursing dan Social Service memiliki dropout rate yang signifikan.
- Mahasiswa laki-laki menunjukkan angka dropout yang lebih tinggi dari perempuan, yang bisa menjadi perhatian lebih lanjut dari pihak institusi.
  
## Rekomendasi Action Items
Berikut beberapa rekomendasi yang dapat diambil oleh Jaya Jaya Institut:
- Targeted Counseling: Fokuskan pendampingan akademik pada mahasiswa dengan kombinasi faktor risiko (utang, tanpa beasiswa, tidak tepat waktu membayar).
- Pemberian Beasiswa Adaptif: Perluas cakupan beasiswa untuk mahasiswa dari jurusan atau latar belakang rentan.
- Monitoring Berkala via Dashboard: Gunakan dashboard secara rutin untuk melihat tren dropout dan intervensi dini.
- Evaluasi Jurusan Berisiko: Audit internal terhadap jurusan dengan tingkat dropout tinggi untuk mengevaluasi kurikulum, beban studi, atau dukungan dosen.
- Peningkatan Sistem Informasi Akademik: Integrasi sistem prediksi dropout ke dalam sistem akademik yang sudah ada agar dapat langsung memberikan alert.
