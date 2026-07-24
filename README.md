# ITDAV-25 Test Set YOLO Annotations

![Dataset](https://img.shields.io/badge/Dataset-ITDAV--25-orange)
![Annotations](https://img.shields.io/badge/Format-YOLOv5%2FYOLOv8-blue)
![Images](https://img.shields.io/badge/Test%20Images-2187-green)
![License](https://img.shields.io/badge/License-Refer%20Original%20Dataset-red)

## Overview

This repository provides **manual YOLO-format object detection annotations** for the **2,187 test images** of the **ITDAV-25 (Indian Thermal Dataset for Autonomous Vehicles)**.

The original ITDAV-25 dataset, available through IEEE DataPort, contains thermal images collected in diverse Indian driving environments for autonomous vehicle research. While the dataset includes training, validation, and test images, the **test split was released without object detection annotations**.

This repository fills that gap by providing **high-quality manually annotated YOLO labels for all 2,187 test images**, enabling researchers to evaluate and benchmark object detection models on the complete ITDAV-25 dataset.

> **Important**
>
> - ✅ This repository contains **only YOLO annotation (.txt) files**.
> - ❌ The original thermal images are **NOT included**.
> - Please download the images from the official IEEE DataPort dataset before using these annotations.

---

# Original Dataset

The original ITDAV-25 dataset is available at IEEE DataPort:

**ITDAV-25: Indian Thermal Dataset for Autonomous Vehicles**

https://ieee-dataport.org/documents/itdav-25-indian-thermal-dataset-autonomous-vehicles

Please cite the original dataset if you use these annotations in your work.

---

# Repository Structure

```
ITDAV-25-Test/
│
├── labels/
│   └── test/
│       ├── 000001.txt
│       ├── 000002.txt
│       ├── ...
│       └── 002187.txt
│
└── README.md
```

This repository contains **only annotation files** corresponding to the original test images.

---

# Annotation Format

Annotations follow the standard **YOLO Object Detection format**.

Each image has a corresponding `.txt` file.

Example:

```
0 0.531250 0.462963 0.156250 0.240741
2 0.726563 0.592593 0.085938 0.166667
```

Each row follows:

```
<class_id> <x_center> <y_center> <width> <height>
```

where

- **class_id** – Object category
- **x_center** – Normalized x-coordinate of bounding box center
- **y_center** – Normalized y-coordinate of bounding box center
- **width** – Normalized bounding box width
- **height** – Normalized bounding box height

All values are normalized between **0 and 1**.

---

# Using the Annotations

## Step 1

Download the original ITDAV-25 dataset from IEEE DataPort.

## Step 2

Extract the thermal images.

## Step 3

Copy this repository's `labels/` folder into the dataset directory while preserving the folder structure.

Example:

```
ITDAV-25/
│
├── images/
│   ├── train/
│   ├── val/
│   └── test/
│
├── labels/
│   └── test/
│
└── data.yaml
```

---

# Training/Evaluation with YOLO

Example `data.yaml`

```yaml
path: /path/to/ITDAV-25

train: images/train
val: images/val
test: images/test

names:
  0: Person
  1: Car
  2: Motorcycle
  3: Bicycle
  ...
```

Evaluate using YOLOv8:

```bash
yolo detect val \
    model=best.pt \
    data=data.yaml \
    split=test
```

---

# Applications

These annotations can be used for:

- Thermal Object Detection
- Autonomous Driving
- Advanced Driver Assistance Systems (ADAS)
- Night-time Object Detection
- Thermal Vision Research
- Benchmarking Deep Learning Models
- Transfer Learning
- Computer Vision Research

---

# Citation

If you use these annotations in your research, please cite both the original dataset and this repository.

### Original Dataset

```bibtex
@dataset{ITDAV25,
  title={ITDAV-25: Indian Thermal Dataset for Autonomous Vehicles},
  publisher={IEEE DataPort},
  year={2025}
}
```

### This Repository

```bibtex
@misc{Gadari2026ITDAV25Annotations,
  author       = {Charitha Gadari},
  title        = {YOLO Annotations for the ITDAV-25 Test Dataset},
  year         = {2026},
  howpublished = {\url{https://github.com/Charithagadari/ITDAV-25-Test}}
}
```

---

# Acknowledgements

We sincerely thank the authors of the **ITDAV-25 (Indian Thermal Dataset for Autonomous Vehicles)** for making the thermal image dataset publicly available through IEEE DataPort.

This repository is an independent contribution that provides **manual YOLO object detection annotations for the complete test split (2,187 images)** to support research in thermal object detection, autonomous driving, and computer vision.

---

# Disclaimer

- This repository **does not redistribute the original ITDAV-25 images**.
- All rights to the thermal images belong to the original dataset authors.
- Users must download the original dataset from IEEE DataPort and comply with its licensing and citation requirements.
- These annotations are provided for **research and educational purposes**.

---

# Author

**Charitha Gadari**

M.Tech, Computer Science and Engineering  
Indian Institute of Information Technology Design and Manufacturing (IIITDM) Kurnool

GitHub: https://github.com/Charithagadari

---

## ⭐ Support

If you find these annotations useful for your research, please consider **starring ⭐ this repository** and citing both the original ITDAV-25 dataset and this annotation repository in your publications.
