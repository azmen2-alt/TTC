# TTC Subway Delay Analysis

**Project Title:** TTC Subway Delay Data (2024–2025) – Comprehensive Analytical Pipeline

**Date Created:** 2025-11-20

**Date Modified:** 2025-12-3

---

## Executive Summary of Key Findings
This project examines TTC Subway Delay Data from **2024** through **October 2025**, applying a full data-science pipeline (data preparation, descriptive analytics, diagnostic analytics, and predictive modelling). The main results are:

1. **Train spacing ("Min Gap") is the strongest determinant of delay severity.**
   In all models and statistical tests, `min_gap` is the most influential predictor of long delays.
2. **Peak and off-peak periods do not differ significantly in delay severity.**
   Independent-samples t-tests show no statistically meaningful difference in mean delays between peak and off-peak times.
3. **Delay patterns vary by line and shift over time.**
   Line 2 (BD) shows the highest mechanical/signal delays in 2024, while Line 1 (YU) becomes the most affected line in 2025.
4. **Mechanical, signal, door, and track-level incidents dominate the incident mix.**
5. **Random Forest is the strongest predictive model.**
   It achieves the highest accuracy and F1-score, capturing non-linear relationships and interactions between time, spacing, and line characteristics.

**Overall conclusion:** Improving control of train spacing (headways) offers the clearest path to reducing long-duration TTC delays.
---

## Table of Contents
1. Introduction
2. Project Overview
3. Data Collection
4. Files and Dataset Setup
5. Requirements
6. Installation
7. How to Run the Program
8. Program Workflow with Code and Sample Outputs
9. Expected Output (Overview)
10. Detailed Analytics Explanation
11. Troubleshooting
12. Sample Input and Output
13. Summary of Findings
14. Credits
---

## 1. Introduction
This project applies Python-based data analysis to TTC Subway Delay Data as part of the **INF1340 – Programming for Data Science** final assignment. It demonstrates how to construct a reproducible, modular pipeline that:

* Cleans and prepares real-world public transit data
* Summarizes and visualizes delay patterns
* Diagnoses underlying causes
* Builds predictive models to classify delay severity

---
## 2. Project Overview

The project delivers a complete analytical workflow that includes:
* **Data Preparation**
* **Descriptive Analytics**
* **Diagnostic Analytics**
* **Predictive Analytics**
* **Visualization**
---

## 3. Data Collection
Source:
**City of Toronto Open Data – TTC Subway Delay Data**
[https://open.toronto.ca/dataset/ttc-subway-delay-data/](https://open.toronto.ca/dataset/ttc-subway-delay-data/)

Dataset fields include:
* Date, Time, Day
* Station, Line, Bound
* Incident Code
* Min Delay, Min Gap
* Vehicle ID

After cleaning: **~16,000 valid delay records**.
---

## 4. Files and Dataset Setup
Place the following files in the **same folder**:

### Program File

```
final_notebook_balfaqih_kalliny_qaisar.py
```

### IMPORTANT: Datasets (rename exactly)

Original Filename: **Final_Input1_Balfaqih_Kalliny_Qaisar.csv**
Rename To:         **ttc-subway-delay-data-2024.csv**

Original Filename: **Final_Input2_Balfaqih_Kalliny_Qaisar.csv**
Rename To:         **TTC Subway Delay Data since 2025.csv**

---
## 5. Requirements

Python 3.x with:

* pandas
* numpy
* matplotlib
* scipy
* scikit-learn

### Imported Packages

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as stats
from sklearn import model_selection, preprocessing, linear_model, tree, ensemble, metrics
from typing import Optional, Dict, Tuple
```
---
## 6. Installation

Install dependencies:

```bash
pip install pandas numpy matplotlib scipy scikit-learn
```

Verify installation:

```bash
python -c "import pandas, numpy, matplotlib, scipy, sklearn; print('All packages installed successfully!')"
```
---

## 7. How to Run the Program

### **Option A — Run as Script**

```bash
python final_notebook_balfaqih_kalliny_qaisar.py
```

### **Option B — Interactive Use**

```python
from final_notebook_balfaqih_kalliny_qaisar import *

df_2024 = load_ttc_data("ttc-subway-delay-data-2024.csv")
df_2025 = load_ttc_data("TTC Subway Delay Data since 2025.csv")

df_2024_clean = clean_ttc_data(df_2024)
df_2025_clean = clean_ttc_data(df_2025)

run_descriptive_analytics(df_2024_clean)
run_diagnostic_analytics(df_2024_clean)
run_predictive_analytics(df_2024_clean)
```
---
## 8. Program Workflow with Code and Sample Outputs
### **8.1 Data Preparation**

**Code**

```python
df_2024 = load_ttc_data("ttc-subway-delay-data-2024.csv")
df_2024_clean = clean_ttc_data(df_2024)
```
**Sample Output**
```
Successfully loaded data
Original rows: 12500 → Final rows: 9820
```
---
### **8.2 Descriptive Analytics**

**Code**

```python
run_descriptive_analytics(df_2024_clean)
```

**Sample Output**

```
Mean delay: 3.84 minutes
Top stations: BLOOR, DUNDAS, ST. GEORGE
```
---
### **8.3 Diagnostic Analytics**
**Code**
```python
run_diagnostic_analytics(df_2024_clean)
```
**Sample Output**
```
Correlation r = 0.61
Regression R² = 0.42
p-value = 0.48
```
---
### **8.4 Predictive Analytics**
**Code**

```python
run_predictive_analytics(df_2024_clean)
```
**Sample Output**
```
Random Forest Accuracy: 0.82
Top feature: min_gap
```
---
## 9. Expected Output (Overview)
You will see:
* Console summaries
* Charts for each stage
* Model performance metrics
---
## 10. Detailed Analytics Explanation
* **Descriptive:** What delays look like
* **Diagnostic:** Why delays occur
* **Predictive:** Whether delays will be long or short
---
## 11. Troubleshooting
Common issues:
* Wrong filenames → FileNotFoundError
* Missing packages → pip install
* Colab runtime crash → Restart runtime
---
## 12. Sample Input and Output
### **Sample Input**
```
2024-01-01,02:00,Monday,SHEPPARD STATION,MUI,0,0,N,YU,5491
```
### **Sample Output**
```
Mean delay: 3.84
Correlation: 0.61
Accuracy: 0.82
```
---
## 13. Summary of Findings
* Train spacing is the top factor
* Peak vs off-peak is not different
* Line 1 and 2 have the most delays
* Mechanical & signal issues dominate
* Random Forest performs best
---
## 14. Credits
* **Ahmed Balfaqih** – 1012820930
* **David Kalliny** – 1008558614
* **Abdullah Qaisar** – 1003065416

Course: **INF1340 – Programming for Data Science**
Instructor: **Dr. Maher Elshakankiri**

---
# License

MIT License
© 2025 University of Toronto – Student Submission (INF1340)
---
<img width="468" height="640" alt="image" src="https://github.com/user-attachments/assets/7b1808fb-5bf1-4d6d-b2f4-3b4d707a4e10" />
