# Mosquito Species Classification using Vision Transformers (ViT)

Identifying mosquito species is a critical task in public health. Different species (*Aedes*, *Anopheles*, *Culex*) transmit distinct pathogens (dengue, malaria, West Nile virus). Manual entomological identification is slow and requires expert training. 

This repository implements an automated image classifier using a **Vision Transformer (`vit_tiny_patch16_224`)** to distinguish between 3 key mosquito species, achieving **98%+ validation accuracy**.

## 📌 Project Overview
- **Data Augmentation:** Strategy optimized for small biological image datasets (random flips, rotations).
- **Architecture:** Fine-tuned Pretrained ViT leveraging patch-based attention for fine-grained morphological features.
- **Performance:** Reached rapid convergence (~99% accuracy within 3 epochs).

## 📦 Dataset & Visuals
The model trains on the Mosquito Dataset for Classification, featuring labeled images of three genera: `AEDES`, `ANOPHELES`, and `CULEX`. 

Below is a look at the target mosquito species analyzed in this project:

![Mosquito Species](mosquito.png)

The notebook automatically handles downloading and extracting the source files via Zenodo.

## 📊 Training Results
The implementation achieves strong validation accuracy almost immediately, showcasing how even lightweight ViT variants handle distinct biological visual patterns effectively:

| Epoch | Train Loss | Train Acc | Val Loss | Val Acc |
| :---: | :--------: | :-------: | :------: | :-----: |
| **1** | 0.6695     | 79.12%    | 0.0641   | 98.33%  |
| **2** | 0.1143     | 96.08%    | 0.1196   | 96.50%  |
| **3** | 0.0398     | 98.71%    | 0.0066   | 100.00% |
| **4** | 0.0417     | 98.58%    | 0.0098   | 99.33%  |
| **5** | 0.0494     | 98.29%    | 0.0682   | 97.67%  |
| **6** | 0.0669     | 97.50%    | 0.0380   | 98.33%  |
| **7** | 0.0315     | 98.67%    | 0.0750   | 97.67%  |
| **8** | 0.0365     | 98.67%    | 0.0253   | 99.33%  |

## 🚀 How to Run
Open the `mosquito_classification.ipynb` notebook in Google Colab, Kaggle, or your local Jupyter environment and run all cells. Make sure you have a GPU enabled for faster training times.

### Installation
Install the necessary packages using the included requirements file:
```bash
pip install -r requirements.txt
