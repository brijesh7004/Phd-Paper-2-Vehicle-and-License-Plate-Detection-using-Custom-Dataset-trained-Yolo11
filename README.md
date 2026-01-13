# YOLO License Plate Detection: Training, Evaluation & Benchmarking

This repository provides a complete end-to-end pipeline for detecting vehicle license plates using the latest YOLO architectures. It covers everything from custom model training to rigorous performance benchmarking between **YOLOv8** and **YOLO11**.

## 📂 Project Structure

The project is divided into three main stages, each contained in its own Jupyter Notebook:

| File Name | Purpose | Key Features |
| --- | --- | --- |
| **`Yolo_Training_Vehicle_licenseplate.ipynb`** | **Model Training** | Dataset download from Roboflow, YOLO11 training, and model exporting. |
| **`Yolo_Model_Evaluator.ipynb`** | **Accuracy Metrics** | Calculation of mAP@50, Precision, Recall, and F1-Score for trained models. |
| **`Compare_yolo_models_final.ipynb`** | **Performance Benchmarking** | Comparing Inference Speed (FPS), Latency, and Confidence between YOLOv8 vs YOLO11. |

---

## 🚀 Step-by-Step Workflow

### 1. Training (`Yolo_Training_Vehicle_licenseplate.ipynb`)

This is the starting point. It prepares the environment and trains the core model.

* **Data Source:** Integrated with the Roboflow API to fetch the "Vehicle License Plate" dataset.
* **Model:** Configured for **YOLO11l** (Large) to balance accuracy and speed.
* **Output:** Generates a `best.pt` weights file used in the subsequent steps.

### 2. Evaluation (`Yolo_Model_Evaluator.ipynb`)

Once the model is trained, this notebook performs a deep dive into its "intelligence."

* **Validation:** Runs the model against a test dataset it hasn't seen before.
* **Visualization:** Automatically generates **Confusion Matrices** and **Precision-Recall curves**.
* **Goal:** Ensures the model isn't just "guessing" but accurately identifying license plates in various conditions.

### 3. Comparison (`Compare_yolo_models_final.ipynb`)

This notebook is used for professional benchmarking to justify why one model version is chosen over another.

* **Head-to-Head:** Compares `YOLOv8l` (Base) vs. `YOLO11l` (Base) vs. `YOLO11l` (Custom Trained).
* **Speed Test:** Measures **Frames Per Second (FPS)** and **Inference Latency** (ms).
* **Results:** According to the logs, **YOLO11l** achieved a almost same higher FPS (~32) and lower latency compared to YOLOv8l (~15 FPS).

---

## 📊 Performance Summary

| Model | Avg Latency (s) | FPS | Avg Confidence |
| --- | --- | --- | --- |
| **YOLOv8l (Base)** | 0.067 | 15 | 89.2% |
| **YOLO11l (Base)** | 0.030 | 33 | 91.3% |
| **YOLO11l (Trained)** | **0.031** | **32** | **86.5%** |

---

## 🛠️ How to Use

1. **Setup Environment:**
Install dependencies required for all three notebooks:
```bash
pip install ultralytics roboflow opencv-python matplotlib pandas

```


2. **Run Training:**
Open `Yolo_Training_Vehicle_licenseplate.ipynb`. Input your Roboflow API key and run all cells to train your custom license plate detector.
3. **Run Evaluation:**
Open `Yolo_Model_Evaluator.ipynb`. Update the path to point to your `best.pt` file to see detailed accuracy metrics.
4. **Run Comparison:**
Open `Compare_yolo_models_final.ipynb` to compare your trained model against base versions to see the speed improvements.

## 💻 Tech Stack

* **Framework:** Ultralytics (YOLOv8 & YOLO11)
* **Language:** Python 3.11
* **Platform:** Google Colab / Kaggle (Tesla T4 GPU)
* **Data Management:** Roboflow API

---

*Developed for Vehicle License Plate Recognition research and benchmarking.*
