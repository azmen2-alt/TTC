# TTC Subway Delay Data (2024-2025) - Comprehensive Analytical Pipeline

**University of Toronto**
**Faculty of Information**
**Master of Information Program**
**INF1340H - Programming for Data Science**

* **Students:** Ahmed Balfaqih (1012820930), David Kalliny (1008558614), Abdullah Qaisar (1003065416)
* **Instructor:** Dr. Maher Elshakankiri
* **Date Created:** 2025-11-20
* **Date Modified:** 2025-12-03

---

## Executive Summary of Key Findings
This project examines TTC Subway Delay Data from **2024** through **October 2025**, applying a full data-science pipeline (data preparation, descriptive analytics, diagnostic analytics, and predictive modelling).

The main results are:
1.  **Train spacing ("Min Gap") is the strongest determinant of delay severity.** In all models and statistical tests, `min_gap` is the most influential predictor of long delays.
2.  **Peak and off-peak periods do not differ significantly in delay severity.** Independent-samples t-tests show no statistically meaningful difference in mean delays between peak and off-peak times.
3.  **Delay patterns vary by line and shift over time.** Line 2 (BD) shows the highest mechanical/signal delays in 2024, while Line 1 (YU) becomes the most affected line in 2025.
4.  **Mechanical, signal, door, and track-level incidents dominate the incident mix.**
5.  **Random Forest is the strongest predictive model.** It achieves the highest accuracy and F1-score, capturing non-linear relationships and interactions between time, spacing, and line characteristics.

**Overall conclusion:** Improving control of train spacing (headways) offers the clearest path to reducing long-duration TTC delays.

---

## Table of Contents
1.  Introduction
2.  Project Overview
3.  Data Collection
4.  Files and Dataset Setup
5.  Requirements
6.  Installation
7.  How to Run the Program
8.  Program Workflow with Code and Sample Outputs
9.  Expected Output (Overview)
10. Detailed Analytics Explanation
11. Troubleshooting
12. Sample Input and Output
13. Summary of Findings
14. Credits

---

## 1. Introduction
This project applies Python-based data analysis to TTC Subway Delay Data as part of the **INF1340-Programming for Data Science** final assignment. It demonstrates how to construct a reproducible, modular pipeline that:
* Cleans and prepares real-world public transit data
* Summarizes and visualizes delay patterns
* Diagnoses underlying causes
* Builds predictive models to classify delay severity

## 2. Project Overview
The project delivers a complete analytical workflow that includes:
* **Data Preparation**
* **Descriptive Analytics**
* **Diagnostic Analytics**
* **Predictive Analytics**
* **Visualization**

## 3. Data Collection
**Source:** City of Toronto Open Data - TTC Subway Delay Data
**URL:** [https://open.toronto.ca/dataset/ttc-subway-delay-data/](https://open.toronto.ca/dataset/ttc-subway-delay-data/)

**Dataset fields include:**
* Date, Time, Day
* Station, Line, Bound
* Incident Code
* Min Delay, Min Gap
* Vehicle ID

After cleaning, the dataset contains approximately **16,000 valid delay records**.

## 4. Files and Dataset Setup
Place the following files in the **same folder**:

### Program File
* `final_notebook_balfaqih_kalliny_qaisar.py`

### IMPORTANT: Datasets (Rename Exactly)
You must rename your input CSV files for the script to recognize them:

| Original Filename | **Rename To** |
| :--- | :--- |
| `Final_Input1_Balfaqih_Kalliny_Qaisar.csv` | **`ttc-subway-delay-data-2024.csv`** |
| `Final_Input2_Balfaqih_Kalliny_Qaisar.csv` | **`TTC Subway Delay Data since 2025.csv`** |

## 5. Requirements
Python 3.x with the following libraries:
* pandas
* numpy
* matplotlib
* scipy
* scikit-learn

## 6. Installation

**Install dependencies via pip:**
```bash
pip install pandas numpy matplotlib scipy scikit-learn
