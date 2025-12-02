# ADSP_31014_Final_Project
CycleGAN Project
This project implements a CycleGAN-based unpaired image-to-image translation pipeline that learns bidirectional mappings between Van Gogh–style paintings and real-world photographs.
It covers dataset analysis, balancing, model training, evaluation, visualization, and deployment via Gradio.

The implementation is built on top of the official PyTorch CycleGAN framework and is designed to run in Google Colab with GPU support.

📌 Project Overview

Task: Unpaired image-to-image translation
Model: CycleGAN (ResNet generators, PatchGAN discriminators)
Domains:
-A → B: Van Gogh paintings → Real photographs
-B → A: Real photographs → Van Gogh paintings

Dataset: vangogh2photo
Framework: PyTorch CycleGAN & Pix2Pix
Interface: Gradio web demo

🔧 Features

✅ Automatic environment setup (from environment.yml)
✅ GPU detection & training
✅ Dataset visualization and analytics
✅ Dataset balancing for stable training
✅ CycleGAN training from scratch
✅ Loss parsing and visualization
✅ Model testing and image comparison
✅ Gradio-based interactive demo
✅ Test-Time Augmentation (TTA) for better outputs


📘 Introduction to CycleGAN

CycleGAN is a generative adversarial network (GAN) designed for unpaired image-to-image translation, where paired training data is unavailable.

Unlike traditional supervised image translation methods, CycleGAN learns mappings between two image domains A and B using two generators and two discriminators:

G<sub>A</sub> : A → B (e.g., Van Gogh paintings → photographs)

G<sub>B</sub> : B → A (photographs → Van Gogh paintings)

D<sub>A</sub>, D<sub>B</sub> discriminate between real and generated images in each domain

To ensure meaningful translation, CycleGAN introduces cycle-consistency loss, which enforces that translating an image from one domain to the other and back should reconstruct the original image:

𝐴→𝐵→𝐴≈𝐴, 𝐵→𝐴→𝐵≈𝐵

In addition to adversarial loss, CycleGAN also uses identity loss to preserve color composition and prevent unnecessary changes when images are already in the target domain.

This design enables CycleGAN to perform realistic style transfer without requiring paired datasets, making it well-suited for tasks such as artistic style transfer, season translation, and domain adaptation.


Sample output:Real vs. CycleGAN-Generated Image
<img width="976" height="506" alt="download" src="https://github.com/user-attachments/assets/b9b855f7-ca7e-4be2-887c-cfb82041ee28" />

