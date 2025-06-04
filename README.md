# Adversarial Attack Dataset for Differential Relays

This repository contains the dataset used in the experiments of our IEEE Transactions on Smart Grid paper:

> **Citation**  
> Ahmad Mohammad Saber, Aditi Maheshwari, Amr Youssef, and Deepa Kundur,  
> *"Adversarial Attacks on Deep Learning-Based False Data Injection Detection in Differential Relays"*,  
> IEEE Transactions on Smart Grid, 2024.

---

## 📁 Dataset File

The dataset is provided as a CSV file:

The_labeled_dataset.csv


It is located in the same directory as this README.

---

## 📄 Description

This dataset supports the experimental evaluation of adversarial attacks against deep learning-based false data injection detection in Line Current Differential Relays (LCDRs). It simulates the behavior of LCDRs protecting line 1–2 in a power system, with one LCDR located near each terminal.

### Event Classes

- **Class A (Label 0)**: Internal faults that **cause the LCDR to trip**
- **Class B (Label 1)**: **False Data Injection Attacks (FDIAs)** that manipulate **remote measurements** but still **trigger the LCDR to trip**

---

## 🔢 Data Structure

Each instance is a **6-dimensional multivariate time series** consisting of:

- 3-phase current measurements (in kA) at the **local end** of the protected line
- 3-phase current measurements (in kA) at the **remote end** of the protected line

### Format

- **Shape**: `6 × 83` (T = 83 time steps per instance)
- **CSV Format**:
  - Each instance is represented in **7 consecutive rows**:
    - 6 rows for the current measurements (each row corresponds to one signal)
    - 1 row for the **Time** values
  - Columns:
    - `Measurement`: Signal name (e.g., `I_12_a`, `I_12_b`, `I_21_a`, etc.)
    - `Label`: Ground-truth class (0 or 1)
    - `t1`, `t2`, ..., `t83`: Current values at each time step

---

## 🧪 Notes

- **Measurement noise** has been added to all signals to simulate **worst-case detection scenarios**
- The dataset covers a variety of realistic scenarios, including:
  - Fault types: single-line-to-ground, double-line, three-phase
  - Varying fault resistances and locations
  - Multiple FDIA strategies: different starting times, affected phases, and trajectories

---

## 📚 How to Cite

If you use this dataset in your work, please cite the following paper:

**Plain Text Citation**:  
Ahmad Mohammad Saber, Aditi Maheshwari, Amr Youssef, and Deepa Kundur,  
"Adversarial Attacks on Deep Learning-Based False Data Injection Detection in Differential Relays,"  
*IEEE Transactions on Smart Grid*, 2024.

**BibTeX Citation**:
```bibtex
@article{saber2024adversarial,
  author    = {Ahmad Mohammad Saber and Aditi Maheshwari and Amr Youssef and Deepa Kundur},
  title     = {Adversarial Attacks on Deep Learning-Based False Data Injection Detection in Differential Relays},
  journal   = {IEEE Transactions on Smart Grid},
  year      = {2024},
}


📄 Dataset License
This dataset is released for academic and non-commercial research use only.

Use is permitted only if the above paper is cited.

Commercial use is not allowed without prior written approval from the first author (Ahmad Mohammad Saber).
