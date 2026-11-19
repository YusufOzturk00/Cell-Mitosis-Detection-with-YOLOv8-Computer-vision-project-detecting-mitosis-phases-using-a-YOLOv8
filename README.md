Cell-Mitosis-Detection-with-YOLOv8-Computer-vision-project-detecting-mitosis-phases-using-a-YOLOv8

https://www.kaggle.com/code/yusufztrk220205019/yusuf-zt-rk-220205019


# MiDeSeC Mitosis Detection - YOLOv8 Training Pipeline

This Jupyter notebook (`yusuf-zt-rk-220205019.ipynb`) implements a complete YOLOv8 training pipeline for mitosis detection on the **MiDeSeC (Ankara University) dataset**.

## 📋 Overview

The notebook performs the following steps:

1. **Data Preparation** - Converts polygon annotations to YOLO format and organizes train/val splits
2. **Baseline Training** - Trains YOLOv8s on raw images
3. **Data Augmentation** - Applies CLAHE preprocessing to enhance image contrast
4. **Enhanced Training** - Retrains YOLOv8s on CLAHE-processed images
5. **Visualization** - Plots training metrics and results

## 🛠️ Dependencies

```bash
pip install ultralytics opencv-python numpy pandas scikit-learn tqdm pyyaml matplotlib
```

## 📁 Dataset Structure Expected

```
/kaggle/input/nusec-and-midesec/Ankara University Datasets/MiDeSeC/
├── train images/
└── annotations/  (polygon format)
```

## 🚀 Usage

Open the notebook in **Kaggle** or **Jupyter** and run cells sequentially. The notebook is designed for GPU-enabled environments.

### Key Paths (Kaggle-specific)
- Working directory: `/kaggle/working/`
- Raw dataset output: `/kaggle/working/datasets/raw_version/`
- Processed dataset output: `/kaggle/working/datasets/processed_version/`
- Model outputs: `/kaggle/working/MiDeSeC_Project/`

## 📊 Pipeline Stages

| Stage | Description | Output |
|-------|-------------|--------|
| 1 | Polygon → YOLO conversion + train/val split | `mitosis_raw.yaml` |
| 2 | YOLOv8s baseline training | `v8_raw_baseline/` |
| 3 | CLAHE contrast enhancement | `processed_version/` |
| 4 | YOLOv8s on enhanced data | `v8_clahe_processed/` |
| 5 | Metrics visualization | Training curves & comparison |

## 🎯 Target Class

- **Class 0**: `mitosis` (mitotic figure detection)

## 📝 Notes

- Originally developed for **Kaggle** environment with GPU support
- Paths are hardcoded for Kaggle's filesystem structure
- For local use, update `BASE_DIR`, `INPUT_DIR`, and output paths accordingly
- The notebook compares baseline vs. CLAHE-enhanced training performance
