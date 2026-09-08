# SIDAPA-Sistem Deteksi Penyakit dan Hama-Padi
This repository contains experiments on **object detection using YOLOv8** to detect diseases and pests affecting rice plants from rice leaf images.

The experiments use a rice plant image dataset collected from rice fields in **Sigi Regency, Central Sulawesi, Indonesia**. Two model configurations with different numbers of classes were developed to explore the effect of class complexity on detection performance.

## Model Configurations

### Model V1 — 5 Classes

Model V1 detects five classes:

* Brown Spot
* Blast
* Rice Leaf Folder
* Bacterial Leaf Blight
* Healthy

### Model V2 — 4 Classes

Model V2 uses four classes:

* Blast
* Rice Leaf Folder
* Bacterial Leaf Blight
* Healthy

The two configurations are **not intended as a competition to determine which model is the best**. Instead, they represent experimental variations that provide a basis for further research, particularly in addressing detection performance when dealing with a larger number of classes or visually similar categories.

## Dataset

The dataset consists of:

* **2,462 images**
* **4,182 bounding boxes**
* Annotation format: YOLO
* Annotation tool: Roboflow
* Dataset split: **80% training, 10% validation, 10% testing**

Dataset distribution:

| Dataset    | Number of Images |
| ---------- | ---------------: |
| Training   |            1,970 |
| Validation |              246 |
| Testing    |              246 |
| Total      |            2,462 |

## Experimental Results

Model performance was evaluated using precision, recall, mAP@50, mAP@50–95, and F1-score.

| Model | Classes | Precision | Recall | mAP@50 | mAP@50–95 | F1-Score |
| ----- | ------: | --------: | -----: | -----: | --------: | -------: |
| V1    |       5 |     89.2% |  76.1% |  84.7% |     63.2% |      82% |
| V2    |       4 |     93.4% |  80.8% |  88.7% |     71.4% |      86% |

## Methodology

The general experimental workflow consists of:

1. Collecting rice plant images.
2. Annotating objects using Roboflow.
3. Splitting the dataset into training, validation, and testing sets.
4. Preparing the dataset in YOLO format.
5. Training the YOLOv8 model.
6. Evaluating performance using precision, recall, mAP, and F1-score.
7. Conducting experiments with different class configurations.
8. Analyzing detection results as a basis for further development.

## Technologies

* Python
* YOLOv8
* Ultralytics
* OpenCV
* NumPy
* Roboflow
* Google Colab / Jupyter Notebook
