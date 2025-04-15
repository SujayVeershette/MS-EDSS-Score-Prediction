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


