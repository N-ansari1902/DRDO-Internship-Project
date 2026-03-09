Follow this link to access the entire project : https://drive.google.com/drive/folders/18xsISNdBw3g1F5ztoDBWN4anm-n2pk2c?usp=sharing


# RADAR Project: X-Band Radar Signal Reverse Simulation Framework

## Project Overview

This repository contains the frameworks, code, and supporting documents for a research project on **X-Band Radar Signal Reverse Simulation** using Deep Learning methodologies.

The core problem addressed is the scarcity of classified, raw radar data required for validating and testing modern maritime and weather surveillance systems. Instead of relying on traditional, complex physics-based simulators, this project proposes an AI-driven "reverse-simulation" approach to reconstruct realistic raw I/Q radar echo signals from more readily available processed data (e.g., tactical maps or radar displays).

The project explores two distinct deep learning architectures to achieve this goal: an **Autoencoder-based framework** and a **Generative Adversarial Network (GAN)-based framework**.

## Frameworks and Methodology

### 1. Autoencoder-Based Reverse Simulation

This is an interpretive, high-fidelity signal reconstruction framework that combines classical signal processing with machine learning.

*   **Objective:** To map processed radar data back to a raw-like signal representation with a focus on minimizing reconstruction error and ensuring system stability.
*   **Methodology:** The framework incorporates the **Radar Range Equation** and accounts for real-world environmental factors such as **atmospheric attenuation** and **clutter/thermal noise**. An **Autoencoder** is trained to learn the compressed feature space of the raw radar signal and then decode it back from the processed input.
*   **Key Results:** The framework demonstrated stable and effective reconstruction, with a minimum accuracy exceeding **85%** in initial validation tests.

### 2. Generative Adversarial Synthesis (cGAN-Based)

This is a generative framework focused on creating highly realistic, statistically accurate raw radar echoes for maritime surveillance applications.

*   **Objective:** To generate new, synthetic, raw I/Q video signals that are virtually indistinguishable from real-world data, conditioned on high-level tactical inputs.
*   **Architecture:** A **Conditional Generative Adversarial Network (cGAN)**, specifically implemented using a **Pix2Pix** architecture, is used to translate visual representations (e.g., tactical maps) into realistic, noisy signal representations.
*   **Hybrid Physics Kernel:** The generative model is guided by a physics kernel that models complex radar phenomena, including:
    *   **The Radar Range Equation**
    *   **Swerling Case 1 & 3** target fluctuation models (simulating large airborne and maritime targets)
    *   **Weibull-distributed sea clutter** to ensure the generated signals accurately reflect the statistical properties of the marine environment.
*   **Key Results:** Achieved a **Structural Similarity Index (SSIM) of >0.85** when comparing the generated signals to ground truth data, confirming the high visual and structural fidelity of the synthetic data.

## Project Contents

| File Name | Framework/Area | Description |
| :---: | :---: | :---: |
| `rad_sim (6).pdf` | Autoencoder | Research paper detailing the **Autoencoder-Based Reverse Simulation Framework** for X-band Radar. |
| `AI_Based_Xband_Radar_Reverse_Simulation (2).ipynb` | Synthetic Data/Code | Jupyter Notebook demonstrating **synthetic raw radar signal generation** (using `numpy` and `matplotlib`). Includes steps for defining abstract radar parameters, applying attenuation, adding AWGN noise, and signal smoothing. |
| `code updated.ipynb` | Synthetic Data/Code | Similar Jupyter Notebook for **synthetic data generation and processing**, likely an updated version or variant of the above. |
| `rad_sim (5).pdf` | GAN | Research paper on **Generative Adversarial Synthesis** using a cGAN for maritime surveillance reverse-simulation. |
| `sv2000_radar_dataset.zip` | Data | A compressed archive containing processed radar data (e.g., `processed/0.png`, `processed/1.png`, etc.) used for training and testing the deep learning models. |
| `Research_Paper_Figures.zip` | Figures | Compressed archive of visualization assets, including the **cGAN architecture**, loss convergence plots, and validation results (e.g., raw vs. processed signal plots, residual error distributions). |
| `Extra_Figures.zip` | Figures | Additional visualizations, notably a file showing a **3D Volumetric Signal** and a simulated **Plan Position Indicator (PPI) Scope View**, confirming the synthetic data's utility on standard radar consoles. |

## Next Steps

We are currently focused on using the cGAN-generated data to test and validate various target detection
