# Deep Learning (First Project) — Dry Bean Dataset Classification

## Overview

This Jupyter Notebook (`DL project`) sets up the initial environment, mounts Google Drive, loads the **Dry Bean Dataset** (`Dry_Bean_Dataset.xlsx`), and performs initial exploratory data analysis (EDA) and class distribution inspection using Python, TensorFlow/Keras, and Scikit-Learn[cite: 2].

The dataset contains **13,611 records** and **17 columns** (16 numerical geometric/shape features and 1 categorical target column `Class`) with no missing values[cite: 2].

---

## Tech Stack & Libraries

* **Data Manipulation:** `numpy`, `pandas`
* **Visualization:** `matplotlib`, `seaborn`
* **Preprocessing & Evaluation:** `scikit-learn` (`train_test_split`, `StandardScaler`, `LabelEncoder`, `ColumnTransformer`, `Pipeline`, metrics, `class_weight`)
* **Deep Learning:** `tensorflow`, `keras`
* **Reproducibility:** Fixed random seed (`SEED = 42`) across `numpy`, `random`, and `tensorflow`[cite: 2]

---

## Environment & Data Loading

1. **Hardware & Framework Check:** Verifies TensorFlow version (`2.21.0`) and checks GPU availability (`GPU Available: True` on a Colab T4 GPU)[cite: 2].
2. **Google Drive Mount:** Mounts Drive at `/content/drive`[cite: 2].
3. **Dataset Import:** Reads `/content/drive/MyDrive/Data of Dl/Dry_Bean_Dataset.xlsx` into a Pandas DataFrame (`df`) with shape `(13611, 17)`[cite: 2].

---

## Dataset Structure & Data Quality

* **Rows:** `13,611`
* **Columns:** `17` (`14` `float64`, `2` `int64`, `1` `object` target column)
* **Missing Values:** `0` nulls across all columns (`df.isnull().sum()`)[cite: 2]

### Features & Target

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Area` | `int64` | Bean area |
| `Perimeter` | `float64` | Bean perimeter |
| `MajorAxisLength` | `float64` | Length of the major axis |
| `MinorAxisLength` | `float64` | Length of the minor axis |
| `AspectRation` | `float64` | Ratio of major axis to minor axis |
| `Eccentricity` | `float64` | Eccentricity of the ellipse with the same moments |
| `ConvexArea` | `int64` | Area of the smallest convex polygon containing the bean |
| `EquivDiameter` | `float64` | Diameter of a circle with the same area as the bean |
| `Extent` | `float64` | Ratio of pixels in the bounding box to the bean area |
| `Solidity` | `float64` | Ratio of bean pixels to convex hull pixels |
| `roundness` | `float64` | Roundness measure |
| `Compactness` | `float64` | Measure of compactness |
| `ShapeFactor1` | `float64` | Shape factor 1 |
| `ShapeFactor2` | `float64` | Shape factor 2 |
| `ShapeFactor3` | `float64` | Shape factor 3 |
| `ShapeFactor4` | `float64` | Shape factor 4 |
| `Class` | `object` | Target bean variety (`7` unique classes)[cite: 2] |

---

## Exploratory Data Analysis (EDA)

### Target Classes (`Class`)

The dataset includes 7 distinct bean classes:
`SEKER`, `BARBUNYA`, `BOMBAY`, `CALI`, `HOROZ`, `SIRA`, `DERMASON`[cite: 2].

### Class Percentage Breakdown

| Class | Share (%) |
| :--- | :--- |
| `DERMASON` | `26.05%` |
| `SIRA` | `19.37%` |
| `SEKER` | `14.89%` |
| `HOROZ` | `14.17%` |
| `CALI` | `11.98%` |
| `BARBUNYA` | `9.71%` |
| `BOMBAY` | `3.84%` |[cite: 2]

### Visualizations Included

* **Class Distribution Bar Chart:** Count plot of `Class` across the dataset[cite: 2].
* **KDE Density Plots by Class:** Distribution plots for `Solidity`, `AspectRation`, and `Perimeter` grouped by `Class`[cite: 2].

---

## Notes on Current Notebook State

* Libraries for preprocessing, class weighting, evaluation metrics, and deep learning are imported and ready for the modeling stage[cite: 2].
* Data loading, null checks, class distribution, and initial KDE plots have been executed[cite: 2].
* Model building, training, and evaluation cells have not yet been added/executed in this snapshot[cite: 2].
