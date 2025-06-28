# Tomato-Leaf-Disease-Classification-with-Transfer-Learning-DenseNet121

## Project Overview

This project utilizes transfer learning with the **DenseNet121** architecture to classify different types of **tomato leaf diseases** from images. Early and accurate detection of plant diseases is essential for improving agricultural productivity and minimizing crop loss.


## Problem Statement

Tomato crops are vulnerable to various diseases that significantly impact yield and quality. Manual disease detection is time-consuming, error-prone, and requires expert knowledge. To solve this, we aim to build an intelligent, automated classification model to detect tomato leaf diseases based on image data.


## Project Objectives

- Build an image classification model using **DenseNet121** and **transfer learning**.
- Predict and identify tomato leaf diseases from uploaded images.
- Evaluate model performance using metrics such as **accuracy**, **precision**, **recall**, and **F1-score**.
- Deploy the model for interactive prediction and real-time use in platforms like **Colab** or **Streamlit**.


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
https://github.com/Faishal-Anwar/Tomato-Leaf-Disease-Classification-with-Transfer-Learning.git
cd /Tomato-Leaf-Disease-Classification-with-Transfer-Learning
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

#### 5. run notebook
Once all dependencies are installed, start the Notebook.
```bash
streamlit run streamlit_app.py
```

## Model Architecture

- **Base Model**: DenseNet121 (pretrained on ImageNet)
- **Top Layers**:
  - `BatchNormalization`
  - `Dense(256, activation='relu')`
  - `Dropout(0.35)`
  - `Dense(120, activation='relu')`
  - `Dense(10, activation='softmax')` for classification


## Training Setup

- **Image Size**: 256x256
- **Loss Function**: Categorical Crossentropy
- **Optimizer**: Adam (learning rate = 0.0001)
- **Batch Size**: 32
- **Epochs**: 100 with EarlyStopping
- **Label Mode**: Categorical (One-hot)


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


## Conclusion

Through the use of **transfer learning** with **DenseNet121**, this project successfully achieved high accuracy in classifying 10 types of tomato leaf conditions, including various diseases and healthy leaves.

Key findings from this project include:

- The model achieved an overall **accuracy of 93.3%**, with **precision, recall, and F1-scores** consistently above 90% across most classes.
- Diseases such as **Tomato Mosaic Virus** and **Healthy leaves** were identified with near-perfect precision and recall.
- The use of transfer learning significantly reduced training time while maintaining strong generalization on validation data.
- Visual tools such as **confusion matrix** and **classification report** provided interpretable insights into class-wise performance.

This model can serve as a powerful assistive tool for farmers and agricultural experts to quickly and accurately identify tomato leaf diseases, enabling early intervention, better crop management, and reduced dependency on manual inspection.
