
## 📊 Dataset: CBIS-DDSM Breast Cancer Image Dataset

This project uses the **CBIS-DDSM (Curated Breast Imaging Subset of DDSM)** dataset, a publicly available and widely used dataset for breast cancer research and deep learning applications.

🔗 Dataset link:
[https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset](https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset)

---

## 🧠 Overview

The CBIS-DDSM dataset is a curated and standardized version of the original **Digital Database for Screening Mammography (DDSM)**. It contains **mammography (X-ray) images** of breast tissue, along with annotations and pathology information.

The dataset is designed to support tasks such as:

* Breast cancer detection
* Mass and calcification classification
* Benign vs malignant classification (binary classification)

---

## 📁 Dataset Structure

The dataset is organized into multiple folders containing images and metadata:

```
cbis_ddsm/
│
├── train/
│   ├── benign/
│   ├── malignant/
│
├── test/
│   ├── benign/
│   ├── malignant/
│
├── csv/
│   ├── metadata files (mass, calcification descriptions)
```

### Key Components:

* **Mammogram Images**

  * Grayscale X-ray images of breast scans
  * Provided in PNG format (converted from DICOM)

* **Classes**

  * **Benign**: Non-cancerous findings
  * **Malignant**: Cancerous findings

* **Annotations**

  * Region of Interest (ROI)
  * Abnormality type:

    * Mass
    * Calcification
  * Shape, margins, and other diagnostic features

---

## 🧾 Data Details

| Feature             | Description                         |
| ------------------- | ----------------------------------- |
| Image Type          | Mammography (X-ray)                 |
| Format              | PNG (converted from DICOM)          |
| Classification Type | Binary (Benign vs Malignant)        |
| Additional Labels   | Mass, Calcification                 |
| Metadata            | CSV files with detailed annotations |

---

## 🧪 Use Cases

This dataset is suitable for:

* CNN-based image classification
* Transfer learning (ResNet, VGG, Inception, MobileNet, ViT)
* Medical image analysis
* Binary classification (Cancer vs No Cancer)
* ROI-based detection tasks

---

## ⚠️ Challenges

* **Class imbalance** between benign and malignant samples
* **High-resolution images** require preprocessing
* **Medical domain complexity** requires careful evaluation

---

## 🛠️ Preprocessing Steps (Typical)

* Image resizing (e.g., 224×224)
* Normalization
* Data augmentation (flip, rotation, zoom)
* Train-test split (if not already provided)

---

## 📌 Notes

* This dataset contains **medical imaging data**, so evaluation metrics like **precision, recall, F1-score, and ROC-AUC** are more important than accuracy alone.
* Proper preprocessing and augmentation significantly improve model performance.

---

If you want, I can also:

* Add **dataset images preview section**
* Write **model section (ResNet, VGG, etc.) for README**
* Or create a **full GitHub README (project + dataset + results + setup)**
