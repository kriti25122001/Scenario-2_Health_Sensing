# Scenario 2 – Health Sensing

This repository contains the solution to **Scenario 2 – Health Sensing [25 Marks]**, a healthcare data science assignment from DeepMedico™. The goal is to detect breathing irregularities (Apnea, Hypopnea) during sleep using multi-modal physiological data collected over 8-hour sessions from 5 participants.

---

## Repository Structure

```
.
├── Visualization/                  # Contains PDF plots for all 5 participants
│   ├── AP01.pdf, AP02.pdf, ...     # Raw signal visualizations with event overlays
│
├── Bonus_task.ipynb               # Sleep Stage Classification (Bonus 5 Marks)
├── Dataset_preparation.ipynb      # Visualization, Filtering, and Window Dataset Creation
├── Modelling.ipynb                # 1D CNN and Conv-LSTM training with LOPO Cross-Validation
├── IITG_assignment_2.ipynb        # Monolithic backup notebook (all tasks combined)
├── README.md                      # Project overview and usage instructions
```



---

## Project Overview

### Objective:
Detect **breathing disorders during sleep** using physiological time-series data and build deep learning models to classify them accurately.

### Dataset Provided:
- **Signals:**
  - Nasal Airflow (32 Hz)
  - Thoracic Movement (32 Hz)
  - SpO₂ (Oxygen Saturation, 4 Hz)
- **Annotations:**
  - Flow Events (Apnea, Hypopnea)
  - Sleep Profile (Sleep Stage Labels: Wake, REM, N1, N2, N3)

---

## Completed Tasks

### 1.Visualization (3 Marks)
- Visualized all signals across the 8-hour session.
- Overlaid annotated breathing events (Apnea, Hypopnea).
- Exported participant-wise plots in PDF format inside `Visualization/`.

### 2.Data Cleaning (4 Marks)
- Applied band-pass filtering to remove high-frequency noise.
- Preserved the breathing frequency range (0.17 Hz – 0.4 Hz).

### 3.Dataset Creation (8 Marks)
- Split cleaned signals into **30-second windows** with **50% overlap**.
- Assigned labels: `Obstructive Apnea`, `Hypopnea`, or `Normal`.
- Created a machine learning-ready dataset.

### 4.Modeling (10 Marks)
- Trained models using:
  - **1D Convolutional Neural Networks (CNN)**
  - **1D Conv-LSTM**
- **Evaluation Strategy:** Leave-One-Participant-Out Cross-Validation (LOPO-CV)
- **Metrics Reported:**
  - Accuracy, Precision, Recall, Sensitivity, Specificity
  - Confusion Matrix (per fold and averaged)

### 5.Bonus Task: Sleep Stage Classification (5 Marks)
- Used sleep stage annotations to classify 30s windows into stages like Wake, REM, N1, N2, N3.
- Reused CNN and Conv-LSTM models for this task.
- Added in `Bonus_task.ipynb`

---

## How to Use

> You can explore the entire pipeline using the individual Jupyter notebooks provided.

- **To visualize signal data:**  
  Open `Dataset_preparation.ipynb` → Run visualization section.

- **To clean and window data:**  
  Use the filtering + dataset creation cells in `Dataset_preparation.ipynb`.

- **To train models for classification:**  
  Open `Modelling.ipynb` and run training + evaluation cells for both CNN and Conv-LSTM.

- **To attempt the bonus sleep stage task:**  
  Check `Bonus_task.ipynb`.

---

## Notes

- `IITG_assignment_2.ipynb` contains the entire workflow in one file and serves as a backup or consolidated version.
- Plots generated during visualization are exported to the `Visualization/` folder in PDF format as required.

---

## Future Improvements

- Add automated `vis.py` and `create_dataset.py` scripts for CLI usage.
- Integrate a dashboard for better visual analysis.
- Implement sleep stage classification with a Transformer-based model.

---

## Author

**Kriti Vajpayee**  
M.Tech – Remote Sensing & GIS  
DeepMedico™ Sleep Sensing Pilot Project  
GitHub: [kriti25122001](https://github.com/kriti25122001)

---
