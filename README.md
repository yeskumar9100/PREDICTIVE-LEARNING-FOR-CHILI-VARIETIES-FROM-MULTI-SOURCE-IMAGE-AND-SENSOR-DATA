Here is a complete, professional `README.md` tailored specifically to your project. You can copy and paste this directly into your GitHub repository.

---

# 🌶️ Intelligent Multi-Source Chili Image Classification

An automated, machine learning-based computer vision system designed to classify chili varieties and assess physical health states from multi-source digital images. This project replaces subjective manual sorting with a scalable, high-throughput predictive model to assist modern Agri-based industries in reducing post-harvest losses and standardizing quality control.

## 📖 Overview

Chili cultivation generates massive volumes of multi-source image data. Traditional visual inspection is labor-intensive, subjective, and unscalable for industrial needs. This project automates the classification of chilies into five distinct categories (varieties and health states) by extracting complex morphological features (texture, shape, color) from preprocessed images and utilizing an optimized Light Gradient Boosting Machine (LGBM) classifier.

## ✨ Key Features

* **Multi-Class Identification:** Classifies images into 5 specific categories:
* *Fresh Varieties:* Bari, Bombai, Cherry
* *Quality/Health States:* Dry, Unhealthy


* **Robust Preprocessing Pipeline:** Automates geometric normalization (64x64 pixels), color space standardization (RGB), and feature flattening (12,288 1D feature vectors).
* **High Efficiency:** Uses data persistence (`.npy` binary files) to drastically reduce computational overhead during training.
* **Real-Time Inference:** Deploys a serialized `.pkl` model to predict the class of unseen, real-world chili images instantly.

## 🧠 Methodology & Workflow

1. **Data Acquisition:** Ingestion of multi-source image data organized by class.
2. **Preprocessing:** Standardizing images to ensure geometric and numerical uniformity.
3. **Data Integration:** Compiling images into a massive Feature Matrix (X) and Label Vector (Y).
4. **Data Splitting:** Randomized and stratified 70% Training / 30% Testing split for unbiased evaluation.
5. **Multi-Model Training:** Simultaneous training of four supervised learning algorithms to find the optimal decision boundaries.
6. **Evaluation & Serialization:** Validating models and saving the best performer using `joblib`.

## 📊 Model Performance

Four supervised machine learning classifiers were evaluated. The **Light Gradient Boosting Machine (LGBM)** outperformed all baselines due to its highly efficient leaf-wise tree growth strategy, which is perfectly suited for high-dimensional image data.

| Algorithm | Accuracy | Precision | Recall | F1-Score |
| --- | --- | --- | --- | --- |
| AdaBoost | 80.80% | - | - | - |
| SVM | 95.20% | - | - | - |
| LDA | 96.00% | - | - | - |
| **LGBM (Proposed)** | **98.93%** | **98.94%** | **98.94%** | **98.94%** |

## 💻 Tech Stack

* **Language:** Python 3.12
* **Image Processing:** OpenCV (`cv2`), Scikit-image
* **Data Handling:** NumPy, Pandas
* **Machine Learning:** Scikit-learn, LightGBM
* **Visualization:** Matplotlib, Seaborn
* **Model Serialization:** Joblib

## ⚙️ System Requirements

* **OS:** Windows 10/11, macOS, or Linux
* **RAM:** 8 GB minimum (16 GB recommended)
* **Storage:** 250 GB minimum (SSD preferred)
* **Processor:** Multi-core processor (Intel i5 / AMD Ryzen equivalent or higher)

## 🚀 Installation & Usage

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/chili-classification.git
cd chili-classification

```


2. **Install the required dependencies:**
```bash
pip install -r requirements.txt

```


3. **Prepare the Data:**
Place your raw chili images into their respective folders within the `dataset/` directory (e.g., `dataset/Bari/`, `dataset/Unhealthy/`).
4. **Run the Preprocessing and Training Pipeline:**
```bash
python train.py

```


*(This will process the images, save `.npy` files, train the models, and save the best LGBM model as a `.pkl` file.)*
5. **Run Inference on a New Image:**
```bash
python predict.py --image path/to/your/test_image.jpg

```



## 🔮 Future Scope

* **Deep Learning Integration:** Implementing Convolutional Neural Networks (CNNs) to extract richer spatial features without requiring manual 1D flattening.
* **Edge Deployment:** Porting the lightweight model to a mobile application or IoT edge device for on-the-field video inference by farmers.
* **Dataset Expansion:** Broadening the training data to include highly specific bacterial diseases and additional regional chili varieties.

---

*Note: Make sure to update the `https://github.com/yourusername/chili-classification.git` link in the Installation section to your actual GitHub repository URL once you create it.*
