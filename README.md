# GAN Monet Style Generation (CycleGAN)

## Project Overview
This project implements a **CycleGAN** model to perform unpaired image-to-image translation from real-world photographs to Monet-style paintings.

The work was completed as part of:
- **Kaggle Competition**: *I'm Something of a Painter Myself*
- **Coursera Course**: *Introduction to Deep Learning – Week 5: GANs* (University of Colorado Boulder)

---

## Dataset
The dataset consists of two unpaired image domains:
- **Photo images**: ~7,000 real photographs
- **Monet images**: ~300 paintings by Claude Monet

There is no one-to-one correspondence between photos and Monet paintings, making CycleGAN the appropriate architecture.

---

## Model Choice: CycleGAN (Photo → Monet)
CycleGAN uses:
- Two generators:
  - G: Photo → Monet
  - F: Monet → Photo
- Two discriminators:
  - DX: distinguishes real vs fake photos
  - DY: distinguishes real vs fake Monet paintings

Key loss components:
- Adversarial loss
- Cycle-consistency loss
- Identity loss (implicit through training stability)

The model was implemented in TensorFlow and trained on Kaggle GPU (Tesla P100).

---

## Training Summary
- Image resolution: **256 × 256**
- Batch size: **4**
- Initial training steps: **200**
- Extended training: **1,000 additional steps**
- Total training time: ~6 minutes on GPU

Losses steadily decreased, and visual quality improved with extended training.

---

## Results
The trained generator successfully produces Monet-style textures, color palettes, and brush-like patterns from input photographs.

A total of **7,000 Monet-style images** were generated and zipped for Kaggle submission.

---

## Kaggle Submission
- Submission file: `images.zip`
- Public Kaggle score: **152.43**
- Leaderboard position visible under the username **Isaac Nowrouzi**

Kaggle competition link:
https://www.kaggle.com/competitions/gan-getting-started

---

## Repository Contents
- `gan-monet-style-generation.ipynb` — Full training and generation notebook
- `README.md` — Project documentation

---

## Author
Isaac Nowrouzi  
GitHub: https://github.com/Rheashopp
