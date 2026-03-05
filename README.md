# 🌿 Plant Identification using Faster R-CNN  

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?logo=pytorch)
![Faster R-CNN](https://img.shields.io/badge/Object%20Detection-Faster%20R--CNN-green)
![CUDA](https://img.shields.io/badge/GPU-CUDA-76B900?logo=nvidia)
![PlantCLEF](https://img.shields.io/badge/Dataset-PlantCLEF%202024-success)
![Research](https://img.shields.io/badge/Project-Academic%20Research-purple)
![PURE Program](https://img.shields.io/badge/Sabanci%20University-PURE%20Research-orange)
![Status](https://img.shields.io/badge/Status-Research%20Project-yellow)

### PlantCLEF 2024 – Deep Learning Based Plant Species Detection

This repository documents a deep learning project developed as part of the **Sabancı University PURE (Program for Undergraduate Research)** and submitted to the **PlantCLEF 2024 plant identification competition**.

The goal of the project is to **automatically identify plant species from images** using **deep learning–based object detection and classification techniques**.

The system is built around a **two-stage Faster R-CNN pipeline** that first detects plant regions in images and then classifies them into plant species.

> ⚠️ **Important Note**  
> Due to the very large dataset and GPU requirements of the project, the experiments were conducted on **Sabancı University laboratory machines with specialized infrastructure**.  
> Therefore **some training scripts and internal processing code are not included in this repository**.

---

# 📊 Project Context

This project was conducted within the:

- **PURE – Program for Undergraduate Research**
- **Sabancı University Computer Vision and Pattern Analysis Laboratory (VPA)**
- **PlantCLEF 2024 Competition**

Team Members:

- Ayça Elif Aktaş  
- Şimal Yücel  
- Doruk Benli  

The project explores **automated plant identification using deep learning techniques**, leveraging large-scale biodiversity datasets provided by the PlantCLEF challenge. :contentReference[oaicite:0]{index=0}

---

# 🌱 Problem Statement

Plant identification is an important task in fields such as:

- agriculture
- environmental science
- biodiversity monitoring
- botany research

Traditional plant classification requires **expert knowledge and manual inspection**, which is time-consuming and difficult to scale.

Deep learning offers a promising solution by allowing models to **learn visual patterns directly from plant images**. :contentReference[oaicite:1]{index=1}

However, the **PlantCLEF dataset introduces a unique challenge**:

- The **training dataset contains images with a single plant label**
- But **test images may contain multiple plant species**

This creates a **multi-instance detection problem**, requiring both:

1. **Plant localization**
2. **Species classification**

---

# 🧠 Proposed Solution

To address this challenge, we designed a **two-stage plant identification pipeline**.

## Stage 1 — Plant Localization

A **pre-trained Faster R-CNN model with a ResNet50 backbone** was used to:

- Detect plant regions
- Generate bounding boxes
- Filter irrelevant detections
- Select the most relevant plant region

Bounding boxes were determined using:

- minimum area filtering
- center weighting
- intersection-over-union (IoU) evaluation

These steps allowed automatic **bounding box annotation across the dataset**.

---

## Stage 2 — Species Classification

Once plant regions were extracted:

- The dataset was converted into **COCO format**
- Bounding boxes were used to train a **fine-tuned Faster R-CNN model**
- Species classification was learned using **Stochastic Gradient Descent (SGD)** optimization

Additional techniques used:

- Data augmentation
- Early stopping
- Training / validation split

This approach enabled the model to **detect plant locations and classify species simultaneously**.

---

# 📦 Dataset

The project uses the **PlantCLEF dataset**, one of the largest biodiversity datasets available.

Dataset characteristics:

- **~1.4 million plant images**
- **~7,800 plant species**
- Images collected from various ecosystems

Due to computational limitations, a subset of **1000 samples** was selected for training experiments.

The dataset was split:

```
80% Training
20% Validation
```

The model achieved **low training loss and stable validation performance**, indicating effective species recognition. :contentReference[oaicite:2]{index=2}

---

# ⚙️ Training Environment

The model training was performed using:

- **PyTorch**
- **Faster R-CNN**
- **ResNet50 backbone**
- **CUDA GPU acceleration**
- **Anaconda environment management**

Training large-scale datasets required **high-performance lab machines**, which is why some internal code and scripts are not included in this repository.



# 🧩 Key Contributions

This project demonstrates:

- Automated plant detection using **Faster R-CNN**
- Bounding box generation for large biodiversity datasets
- Conversion of plant datasets to **COCO format**
- Deep learning–based plant species classification
- A scalable pipeline for **automated plant recognition**

---

# 🚧 Repository Note

This repository serves as a **documentation and research overview** of the project.

Due to:

- extremely large dataset size
- GPU infrastructure requirements
- university lab environment restrictions

some internal scripts used in the training pipeline are **not included in this repository**.

---

# 🔬 Future Work

Potential improvements include:

- Training on the **full PlantCLEF dataset**
- Experimenting with **Vision Transformers (ViT)**
- Using **EfficientNet or SE-ResNeXt architectures**
- Multi-plant detection using improved region proposals

---

# 📚 References

Key research and datasets used in this project include:

- PlantCLEF biodiversity challenge
- iNaturalist dataset
- Faster R-CNN object detection
- CNN-based plant classification research

More detailed references can be found in the original project report.

---

# 📜 License

This repository is intended for **academic and research documentation purposes**.

Dataset usage follows **PlantCLEF dataset licensing terms**.

---
