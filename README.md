# GAN-and-Diffusion-Augmentation-

## Overview
This repository contains a research-oriented implementation notebook that follows the methodology described in the reference study on **plant disease data augmentation using Diffusion models vs GANs**, with the goal of improving segmentation performance (mIoU) through synthetic augmentation and iterative refinement.

The code is provided as a single, finalized Jupyter notebook intended to be executed end-to-end (recommended: Google Colab with GPU).

---

## Reference Paper (Research Basis)
**Paper:** Muhammad et al., *Frontiers in Plant Science*, 2023  
**Topic:** Plant Disease Augmentation: Diffusion vs GAN — mIoU

This implementation is structured to mirror the paper’s practical pipeline: dataset preparation, baseline segmentation training, augmentation using generative models (GAN and Diffusion), pseudo-labeling, and iterative self-training to improve segmentation quality.

---

## Objectives
1. Compare augmentation strategies based on:
   - Generative Adversarial Networks (GANs)
   - Denoising Diffusion models (DDPM-style diffusion)
2. Evaluate the impact of synthetic augmentation on segmentation performance (mIoU).
3. Apply iterative self-training / pseudo-label refinement to reduce underfitting and improve generalization.

---

## Method Summary (High-Level)
The notebook implements a workflow consistent with the paper’s reported improvements:
- **Segmentation backbone**: U-Net family variants (e.g., U-Net++) with strong encoders (e.g., EfficientNet)
- **Augmentation sources**:
  - GAN-generated samples
  - Diffusion-generated samples
- **Pseudo-labeling**: classical/weak-supervision mask generation and refinement
- **Iterative self-training**: multiple rounds of training using improved labels and synthetic data
- **Training optimization**: augmentation policies and learning-rate scheduling (e.g., OneCycleLR), plus mixed precision where applicable

> Note: Exact architectural/training choices are implemented directly inside the notebook.

---

## Repository Contents
- `final_diffusion_and_Gan_implementation_of_research_paper.ipynb`  
  Final implementation notebook (primary artifact).
- `README.md`  
  Project documentation (this file).

---

## Dataset and Data Access
This project is designed to work with the PlantVillage plant disease dataset (via Kaggle).  
The notebook includes steps for downloading and organizing the dataset for training/validation.

---

## Environment / Requirements
Recommended environment:
- **Google Colab**
- **GPU**: NVIDIA T4 (recommended for reasonable runtime)

Software (typical):
- Python 3.x
- PyTorch + CUDA
- Common ML utilities used in the notebook (installed inside the notebook as needed)

---

## How to Run (Reproducible Steps)
1. Open `final_diffusion_and_Gan_implementation_of_research_paper.ipynb`.
2. (Recommended) Click **Open in Colab**.
3. In Colab: `Runtime → Change runtime type → GPU (T4 recommended)`.
4. Run cells **top to bottom** without skipping to ensure correct setup.
5. Review outputs for:
   - dataset download and preparation logs
   - training curves / metrics
   - qualitative results (generated samples / segmentation masks), if produced

---

## Experimental Notes (What to Report in a Research/Academic Submission)
If you are writing a report, the following items are typically expected:
- Dataset used and preprocessing details
- Train/validation/test split protocol
- Model architecture and encoder choice
- Loss functions and evaluation metrics (especially mIoU)
- Augmentation settings (GAN vs Diffusion) and sample counts
- Self-training procedure (number of rounds, pseudo-labeling method)
- Compute environment (GPU type, runtime)
- Final quantitative results and qualitative examples

---

## Reproducibility and Limitations
- Results may vary due to randomness (seeds), GPU differences, and training-time constraints.
- For strict reproducibility, fix random seeds and keep library versions consistent.

---

## Citation
If you use this repository in academic work, cite the original paper (Muhammad et al., 2023, *Frontiers in Plant Science*) and additionally cite this repository (add your GitHub URL) as an implementation resource.

---

## Original Author Notes (Preserved Verbatim)
kaggle username- akshatsajwan05

kaggle key - plantdisease

for opening code please view file name diffusion final_diffusion_and_Gan_implementation_of_research_paper.ipynb this is finaliszed code file
