# Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data

[![Conference](https://img.shields.io/badge/Conference-ICITI%202025-blue)]()

This repository contains the official code and research documentation for the paper **"Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data"**, accepted/submitted to ICITI 2025.

## 🧠 Overview
This repository contains the implementation and findings for our research on resource-efficient visual image reconstruction from fMRI data[cite: 1]. While state-of-the-art deep learning models for brain decoding require massive GPU clusters and weeks of training, this project demonstrates that a lightweight, computationally efficient solution can achieve significant results[cite: 1]. 

Our work introduces a lightweight U-Net architecture designed to reconstruct images from the Generic Object Decoding (GOD) dataset[cite: 1]. By leveraging Principal Component Analysis (PCA) for dimensionality reduction alongside robust regularization (Mix-up augmentation), we successfully navigated the challenge of scarce fMRI data[cite: 1]. Our advanced model achieves meaningful structural similarity scores (SSIM $\approx$ 0.24) in just minutes of training, establishing a critical performance-to-cost benchmark in the neuroscience and computer vision fields[cite: 1].

## 📂 Repository Structure

- 📄 **`Research_18.ipynb`** — Model implementation **with PCA** (Dimensionality reduction applied to fMRI data before reconstruction).
- 📄 **`Research_21.ipynb`** — Model implementation **without PCA** (Direct end-to-end reconstruction).
- 📑 **`ICITI 2025.pdf`** — The main research paper containing the conference proceddings.
- 📝 **`Sayandip Ghosh Research.docm`** — Extended research documentation, literature review, and detailed experimental analysis.

## ⚙️ Dependencies & Requirements

To run the Jupyter Notebooks, you will need the following Python libraries installed:
- `torch` (PyTorch)
- `torchvision`
- `numpy`
- `Pillow`
- `jupyter`

## 🚀 Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/Lightweight-CNN-fMRI-Reconstruction.git
   cd Lightweight-CNN-fMRI-Reconstruction
