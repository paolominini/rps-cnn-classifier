# ✊✋✌️ Rock, Paper, Scissors: CNN Classification & Domain Shift

## 📖 Overview
This project explores the design, training, and evaluation of Convolutional Neural Networks (CNNs) for hand gesture classification ("Rock", "Paper", "Scissors") using the [Rock-Paper-Scissors Kaggle Dataset](https://www.kaggle.com/datasets/drgfreeman/rockpaperscissors). Three models of incremental complexity were developed: a shallow baseline, a deep unregularized network, and a deep regularized network utilizing Dropout and Hyperband tuning. 

While the unregularized model achieved a near-perfect **99% accuracy** on the in-distribution test set, a custom Out-of-Distribution (OOD) Generalization Test revealed severe environmental overfitting. Ultimately, the regularized model proved to be the only architecture capable of surviving a real-world domain shift, highlighting the mathematical necessity of algorithmic regularization.

👉 **For a full, in-depth scientific analysis, please read the full [Project Report (PDF)](./Report.pdf).**

## 📊 Key Results: The Domain Shift
The models were trained on a dataset with a uniform green-screen background. When tested on real-world, out-of-distribution (OOD) images (complex backgrounds, different lighting), the unregularized model catastrophically failed, while the regularized model survived:

| Model | Architecture | In-Distribution (Test) Accuracy | Out-of-Distribution (Real World) Accuracy |
| :--- | :--- | :---: | :---: |
| **Model 1** | Shallow Baseline | 98.0% | 45.2% |
| **Model 2** | Deep Unregularized | **99.0%** | 33.3% *(Random Guessing)* |
| **Model 3** | Deep Regularized (Dropout + Hyperband) | 98.0% | **57.1%** |

## 🗂️ Repository Structure
```text
├── data/                   # (⚠️ Not in repo) Get the data from Kaggle (link above) & personal images
├── models/                 # (⚠️ Not in repo) Download the .keras models from the GitHub "Releases" tab!
├── notebooks/              # Jupyter notebooks containing the training and evaluation pipelines
├── Report.pdf              # Comprehensive project report and architectural justifications
└── README.md               # Project overview