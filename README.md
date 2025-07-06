# Enhanced Residual Autoencoder for ECG Signal Denoising  

Official repository for the article: **"Enhanced Residual Autoencoder for ECG Signal Denoising: A Comparative Study"** by Ramin Goudarzi et al.

**Repository Structure:**

.
├── data/                     # Preprocessed ECG data and noise files  
├── models/                   # Model architectures (e.g., FCN-DAE, DRNN, FCN-DAE_RES)  
├── train/                    # Training scripts and logs  
├── test_results/             # Predictions and test outputs for analysis  
├── results/                  # Saved training metrics and comparative analysis  
├── snr_distribution/         # SNR improvement and RMSE analysis  
├── model_figures/            # Architecture diagrams (.drawio and PNGs)  
│   ├── res.drawio            # FCN-DAE_RES model with residual connections  
│   ├── without_residual.drawio # FCN-DAE without residual connections  
│   └── *.png                 # Exported figures for publication  
├── sampled_denoised_plots/   # High-resolution ECG signal comparisons (noisy vs. denoised)  
├── data.ipynb                # Data loading/preprocessing  
├── FCN_DAE_RES.ipynb         # Training script for FCN-DAE_RES  
├── persample.ipynb           # SNR/RMSE analysis for model comparison  
├── sampled_denoised_for_the_plot.ipynb  # Signal visualization for figures  
├── finall.docx               # Final paper draft  
└── README.md                 # This file  

---

## 📘 Overview

This repository contains all code and data needed to reproduce the experiments in our paper on **ECG denoising using residual autoencoders**. The study evaluates four models (DRNN, FCN-DAE-REF, FCN-DAE-NORES, FCN-DAE-RES) for noise suppression in ECG signals, with a focus on preserving critical clinical features.

Key features:
- **MIT-BIH Arrhythmia Dataset** with Noise Stress Test Database  
- **Reproducible data pipeline** (resampling, noise addition, train/test splits)  
- **Model architectures** (FCN-DAE, FCN-DAE_RES, DRNN)  
- **Metrics:** SNR improvement, PRD, RMSE  
- **Jupyter notebooks** for analysis, plotting, and ablation studies  

---

## 📥 Requirements

Install dependencies (preferably in a virtual environment):

pip install -r requirements.txt

---

## ▶️ Usage

1. **Download Datasets**  
   - MIT-BIH Arrhythmia Database: https://physionet.org/content/mitdb/1.0.0/  
   - Noise Stress Test Database: https://physionet.org/content/nstdb/1.0.0/  
   Place datasets in `/data/` and use `data.ipynb` for preprocessing.

2. **Train Model**  
   Edit hyperparameters in `FCN_DAE_RES.ipynb` and run the training pipeline:  
   jupyter notebook FCN_DAE_RES.ipynb

3. **Evaluate Performance**  
   Use `persample.ipynb` and `sampled_denoised_for_the_plot.ipynb` for:  
   - SNR/RMSE analysis  
   - Visualization of noisy vs. denoised signals  
   - Comparison of models on the test set

4. **Generate Paper Figures**  
   Run `sampled_denoised_for_the_plot.ipynb` to create journal-quality plots for your manuscript.

---

## 📝 Notes

- **Preprocessing** ensures all ECG signals are uniformly resampled to 512 samples.  
- **Noise addition** is randomized per epoch for robustness (see `data.ipynb`).  
- **Reproducibility**: Random seeds are fixed for deterministic experiments.

---

## 📄 License

MIT License. Use and modify freely for academic purposes.

---

## 📬 Citation

If you use this code or data in your work, please cite:

Goudarzi, R., Mikaeelzadeh, K., Miri, M., & Shamsaei Zafarghandi, M. (2025).  
Enhanced Residual Autoencoder for ECG Signal Denoising: A Comparative Study.
