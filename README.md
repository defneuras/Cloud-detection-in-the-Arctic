# Cloud-detection-in-the-Arctic
# Arctic Cloud Masking – MSc Dissertation

This repository contains the code and workflows supporting my MSc dissertation:  
**“Cloud–Snow Discrimination in Sentinel-2 Imagery for Inuit-led Mapping in Pond Inlet”** (University College London, 2025).

The project evaluates the performance of multiple cloud detection approaches over high-albedo Arctic surfaces, with a focus on supporting Inuit-led mapping initiatives such as **Sikumik Qaujimajjuti** and **SIKU**.

---

## 📂 Repository Structure

Arctic-CloudMasking-MSc/
│
├── notebooks/ # Jupyter notebooks for reproducibility
│ ├── 01_patch_extraction.ipynb
│ ├── 02_cnn_training.ipynb
│ ├── 03_kmeans_clustering.ipynb
│ └── 04_evaluation_metrics.ipynb
│
├── src/ # Core Python scripts
│ ├── preprocessing.py
│ ├── cnn_model.py
│ ├── kmeans_model.py
│ └── evaluation.py
│
├── figures/ # Example outputs (optional)
├── requirements.txt # Python dependencies
├── LICENSE # MIT license
└── README.md # This file

---

## 🚀 Methods

The dissertation compared four cloud detection approaches on Sentinel-2 Level-2A imagery:

1. **Scene Classification Layer (SCL)** – ESA baseline mask.  
2. **Brightness threshold** – simple rule-based method (B04 + B08 – B11).  
3. **K-Means clustering** – unsupervised spectral clustering baseline.  
4. **Convolutional Neural Networks (CNNs)** – supervised deep learning model trained on manually labelled patches.

Evaluation metrics included **Precision, Recall, F1-score**, and the **Clear Pixel Gain Index (CPGI)**.  
Seasonal stratification was applied to distinguish between **snow-dominated tiles (March–April)** and **heterogeneous tiles (May–June)**.

---

## 📊 Results Summary

- **CNNs** performed best under snow-dominated winter conditions, reducing snow–cloud confusion.  
- **K-Means** outperformed CNNs in late spring/early summer when spectral contrast was stronger.  
- **Brightness thresholding** was efficient but prone to over-masking snow.  
- **SCL** consistently underperformed compared to alternative methods.  

This seasonal evaluation supports **adaptive model selection**: CNNs for winter/spring, K-Means for summer transition periods.

---

## 🔧 Installation & Usage

Clone the repository:

```bash
git clone https://github.com/<your-username>/Arctic-CloudMasking-MSc.git
cd Arctic-CloudMasking-MSc


Run notebooks in order:

01_patch_extraction.ipynb – Prepare Sentinel-2 patches.

02_cnn_training.ipynb – Train CNNs.

03_kmeans_clustering.ipynb – Apply K-Means.

04_evaluation_metrics.ipynb – Compute metrics and visualise outputs.
