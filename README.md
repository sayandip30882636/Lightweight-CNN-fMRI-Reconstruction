# Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data

[![Conference](https://img.shields.io/badge/Conference-ICITI%202025-blue)]()

This repository contains the official code and research documentation for the paper **"Lightweight Convolutional Neural Network for Visual Image Reconstruction from fMRI Using Limited Data"**, accepted/submitted to ICITI 2025.

## 🧠 Overview
Reconstructing visual images from human brain activity (fMRI signals) is a highly complex challenge, especially when working with limited data. This Research introduces a lightweight Convolutional Neural Network (CNN) designed to efficiently decode and reconstruct images from the **GOD (Generic Object Decoding)** fMRI dataset. 

To evaluate performance and optimize computational efficiency, this repository provides two distinct pipeline variations: one leveraging **Principal Component Analysis (PCA)** for dimensionality reduction, and one without.

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
