# 🚀 Elevate Data Analyst Internship - Task 1: Data Cleaning and Preprocessing

## Project Overview

This repository documents the completion of **Task 1: Data Cleaning and Preprocessing**, a foundational project for the Elevate Data Analyst Internship. The goal was to transform a raw, messy dataset into a clean, structured, and analysis-ready format by systematically addressing common data quality issues.

| Feature | Detail |
| :--- | :--- |
| **Dataset Used** | Medical Appointment No Shows (sourced from Kaggle) |
| **Tool Stack** | Python (Pandas) |
| **Deliverables** | `data_cleaning.ipynb` (Code), `cleaned_medical_appointments.csv` (Output), and this `README.md`. |

***

## 🛠️ The Data Cleaning Pipeline (6 Core Steps)

The cleaning process was executed using **Pandas** in a structured Jupyter Notebook environment, adhering to the principles of data standardization and integrity.

### 1. Standardization of Column Headers ✨
* **Action:** Applied a global transformation to ensure all column names are clean and consistent.
* **Method:** Converted all headers to **snake\_case** (e.g., `PatientId` $\rightarrow$ `patient_id`) by enforcing lowercase and replacing spaces and hyphens with underscores.

### 2. Duplicate Removal 🗑️
* **Action:** Checked for and eliminated any rows that were exact duplicates of previous entries.
* **Method:** Utilized the powerful `df.drop_duplicates(inplace=True)` command.
* **Impact:** Ensures that aggregate statistics and model training are not skewed by redundant records.

### 3. Data Type Integrity Check (D-Type Fixes) 📆
* **Action:** Verified and corrected the data types for critical columns.
* **Method:**
    * Converted `scheduledday` and `appointmentday` from generic string objects to native **`datetime64[ns]`** objects using `pd.to_datetime()`. This enables accurate time-based calculations.
    * Ensured the `age` column was correctly cast as a reliable **integer** type.

### 4. Text Standardization for Categorical Data 🔡
* **Action:** Ensured all text-based categories were consistent to prevent misclassification.
* **Method:**
    * **`gender`**: Converted all values to **uppercase** (e.g., 'F', 'M') for uniformity.
    * **`neighbourhood`**: Used `.str.strip()` to remove unseen whitespace, followed by `.str.title()` for consistent naming.

### 5. Handling Data Quality Issues (Impossible Values) 🩹
* **Action:** Addressed known illogical entries within the dataset.
* **Method:** Filtered out and removed all rows where the `age` value was **negative** (`age < 0`), as this is physically impossible and an indicator of bad data collection.

### 6. Final Data Preparation
* **Action:** The dataset was saved to a new CSV file.
* **Output:** The result is `cleaned_medical_appointments.csv`, which is immediately ready for Exploratory Data Analysis (EDA) and subsequent predictive modeling.

***

## ✅ Key Deliverables

* **`data_cleaning.ipynb`**: The interactive Python code demonstrating the entire cleaning process step-by-step.
* **`cleaned_medical_appointments.csv`**: The final, high-quality, analysis-ready dataset.
* **Short Summary of Changes**: (Integrated into this README for conciseness).

This project provided hands-on experience in the most critical phase of the data analysis lifecycle: **Data Preprocessing**.
