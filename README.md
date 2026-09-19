# 🧠 Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data

[![Conference](https://img.shields.io/badge/Conference-ICITI%202025-blue?style=for-the-badge)]()
[![Paper Status](https://img.shields.io/badge/Status-Accepted-success?style=for-the-badge)]()
[![Field](https://img.shields.io/badge/Domain-Neuroscience%20%26%20Computer%20Vision-orange?style=for-the-badge)]()

**Authors:** Sayandip Ghosh, P. Sathya, and A. S. Dibu  
**Affiliation:** Christ (Deemed to be University), Bangalore, Karnataka, India  

---

## 📖 Overview

This repository contains the official research documentation and findings for our paper **"Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data"**, presented at ICITI 2025.

While state-of-the-art deep learning models for brain decoding require massive GPU clusters and weeks of training, this project demonstrates that a lightweight, computationally efficient solution can achieve significant results. 

Our work introduces a lightweight U-Net architecture designed to reconstruct images from the Generic Object Decoding (GOD) dataset. By leveraging Principal Component Analysis (PCA) for dimensionality reduction alongside robust regularization (Mix-up augmentation), we successfully navigated the challenge of scarce fMRI data. Our advanced model achieves meaningful structural similarity scores (SSIM ≈ 0.24) in just minutes of training, establishing a critical performance-to-cost benchmark in the neuroscience and computer vision fields.

---

## 📂 Repository Structure

Since this repository focuses strictly on academic documentation and findings rather than source code, it includes the following files:

- 📑 **`ICITI 2025.pdf`** — The main research paper containing the official conference proceedings.
- 📝 **`Main Paper.pdf`** — Extended research documentation, literature review, and detailed experimental analysis.

---

## 📊 Dataset Specifications

*   **Source:** Generic Object Decoding (GOD) dataset (Horikawa-Kamitani Lab).
*   **Scope:** Focuses on data collected from Subject 1, encompassing 1,200 training images and 50 testing images.
*   **Preprocessing:** fMRI signals from the visual cortex were normalized using Z-score standardization. Test data was smoothed by averaging 35 fMRI scans over the same test images to obtain cleaner signals.
*   **Image Standardization:** Stimulus images were resized to 64x64 pixels in grayscale and scaled to a range of `[0.0, 1.0]`.

---

## 🔬 Methodology

We conducted a comparative study exploring two distinct architectural pipelines to evaluate the necessity of intelligent data preprocessing in low-resource environments.

### 1️⃣ Baseline Method (Direct Reconstruction)
*   **Input:** Utilizes the full, high-dimensional fMRI vector (3,444 features) without any dimensionality reduction.
*   **Architecture:** A simple feed-forward Encoder-Decoder model without skip connections, relying on sequential information flow.
*   **Training:** Optimized using a combination of Mean Squared Error (MSE), L1, and Perceptual Loss (via frozen VGG-16 weights).
*   **Outcome:** This lightweight model (~11.26M parameters) collapsed into generating identical generic patterns regardless of the fMRI input, highlighting the curse of dimensionality on raw neural data.

### 2️⃣ Advanced Method (Preprocessing-Informed Reconstruction)
*   **Input:** Employs PCA to compress the raw voxel count into 1,000 principal components, denoising the data and capturing the most variance.
*   **Architecture:** A shallow U-Net model containing contraction-expansion paths. Skip connections are utilized to retain high-resolution spatial information essential for accurate image generation.
*   **Training:** Trained using L1 and Perceptual Loss, combined with advanced Mix-up augmentation (creating linear combinations of fMRI-image pairs) to prevent overfitting.
*   **Outcome:** With ~17.97M parameters, this hybrid model successfully learned to map pre-processed neural data into meaningful image space, completely avoiding mode collapse.

---

## 📈 Key Results

Our quantitative and qualitative evaluations on the held-out test set confirm the viability of the Advanced PCA + U-Net architecture. 

### Quantitative Analysis

The Advanced model outperformed the baseline across multiple perceptual and error-based metrics, proving that intelligent preprocessing combined with spatial preservation yields superior structural fidelity.

| Metric | Baseline Model (No PCA) | Advanced Model (With PCA) |
| :--- | :--- | :--- |
| **SSIM** *(Higher is better)* | 0.2425 | **0.2438** |
| **PSNR (dB)** *(Higher is better)*| 11.2559 | **11.2659** |
| **LPIPS** *(Lower is better)* | 0.6208 | **0.6108** |
| **MAE** *(Lower is better)* | 0.2307 | **0.2300** |
| **Parameters** | ~11.26M | **~17.97M** |
| **Estimated Training Time** | ~2 min | **~4 min** |

### Qualitative Analysis

*   🖼️ **Advanced Model:** Successfully reproduced structural and spatial features of ground truth images, such as the vertical panes of a stained-glass window and the general outline of an animal, despite the low resolution.
*   ❌ **Baseline Model:** Demonstrated complete mode collapse, producing a trivial, identically patterned output for every single test sample. 
*   ⚡ **Efficiency Benchmark:** Compared to heavyweight diffusion and GAN-based models (which utilize 50M to 600M+ parameters and require extensive high-end GPU clusters), our U-Net achieves its results with approximately 18M parameters in roughly **4 minutes of training on a single GPU**. 

---

## 🎯 Conclusion

This research provides a functional proof-of-concept that resource-efficient brain decoding is entirely feasible. By aggregating highly noisy voxel features through PCA and preserving spatial details via a lightweight U-Net, we establish a practical alternative to computationally prohibitive models. 

This methodology paves the way for accessible, real-time clinical applications such as stroke rehabilitation and communication aids for "locked-in" patients, where rapid inference and low computational overhead are critical.

---
*For further academic inquiries or discussions regarding this research, please refer to the attached conference proceedings or reach out via the contact information provided in the paper.*
