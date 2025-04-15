# MS-EDSS-Score-Prediction

# A Deep Learning Hybrid Approach for EDSS Prediction Using Brain MRI and Lesion Segmentation

## Project Overview

This project presents a novel hybrid deep learning framework to predict the Expanded Disability Status Scale (EDSS) in patients with Multiple Sclerosis (MS) using brain MRI data and lesion segmentation. It integrates radiomic, volumetric, and clinical features with CNN-based image regression and ensemble learning.

Key Highlights:
- Uses multimodal MRI (T1, T2, FLAIR) and lesion masks
- Combines radiological biomarkers with clinical assessments
- Implements deep CNNs for feature extraction
- Applies multiple regression models with Leave-One-Out Cross-Validation (LOOCV)

---

## Features Used

- **Radiomic**: Lesion volume, count, mean size, contrast ratio
- **Volumetric**: Brain volume, lesion load across modalities
- **Clinical**: Age, gender, symptoms, treatments
- **Deep Visual**: CNN embeddings from axial MRI slices

---
![image](https://github.com/user-attachments/assets/e9811a51-0531-4094-850a-87f0f4abcd9a)

SVR and Ridge showed the best performance, highlighting the importance of nonlinear modeling and regularization.

---

## 📁 Project Structure

```
EDSS_Prediction/
├── data/                          # Patient-wise MRI and lesion data
│   ├── Patient-01/
│   │   ├── T1.nii
│   │   ├── T2.nii
│   │   ├── FLAIR.nii
│   │   ├── LesionSeg_FLAIR.nii
│   │   └── LesionSeg_T2.nii
│   │   └── LesionSeg_T1.nii
│   └── clinical_data.csv          # Clinical features + EDSS scores
│
├── Training_1.ipynb          # Image/mask preprocessing, model building, training, testing
├── requirements.txt          # Python dependencies
└── README.md
```

---

## 🧠 File Descriptions

| File                     | Description |
|--------------------------|-------------|
| Training_1.ipynb | Computes lesion volume, count, contrast ratio, and brain volume,Defines the CNN used to embed axial MRI slices, Trains CNN on FLAIR, T1, T2 slices and saves embeddings, Loads features and embeddings, trains multiple regressors with LOOCV, Tests the saved model on new patient data, Utility functions for NIfTI loading, masking, and processing |

---

## 🔧 Setup Instructions

```bash
# Clone the repository
git clone https://github.com/SujayVeershette/MS-EDSS-Score-Prediction.git
cd MS-EDSS-Score-Prediction

# Create a virtual environment
python -m venv env
source env/bin/activate  # On Windows use: env\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

## 🚀 Running the Pipeline

### 1. Extract radiomic features
Run all cells

### 2. Train CNN and save embeddings
Run all cells

### 3. Run ensemble regression with LOOCV
Run all cells

### 4. Evaluate model on new test patient
Add testing data and feed it to CNN. Later combine tabular features and image embeddings to feed it to the regressor and best model with best metrics are shown 

---

## 📊 Features Used

- Lesion Volume (per modality)
- Lesion Count
- Mean Lesion Size
- Contrast Ratio (T2 vs FLAIR)
- Brain Volume (T1)
- CNN Embeddings (from MRI slices)
- Clinical Features (age, onset, symptoms, treatment, gender)

---

## 🧪 Evaluation Metrics

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score

---

## 📌 Notes

- All MRI files must be in NIfTI format and stored under `/data/Patient-ID/`.
- Lesion masks should be aligned and binarized (0s and 1s).
- `clinical_data.csv` must include EDSS and clinical variables per patient.
- Leave-One-Out Cross-Validation (LOOCV) is used for robust performance evaluation.



