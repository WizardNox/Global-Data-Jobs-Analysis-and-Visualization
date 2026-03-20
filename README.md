# Global Data Jobs Analysis and Visualization (EDA) (Power BI)

## Project Overview

The Global Data Jobs Analysis project is an end-to-end exploratory data analysis (EDA) and visualization study of the global data job market. The objective of this project is to extract meaningful insights from real-world job posting data and understand how factors such as role, salary, location, skills, and work type influence compensation and hiring trends.

The project combines Python-based data analysis with Power BI dashboards to deliver both statistical rigor and business-oriented insights. Using Python, the dataset was cleaned, transformed, and analyzed to uncover patterns in salary distribution, missing data behavior, and variability across roles. Key statistical techniques such as skewness analysis, standard deviation, coefficient of variation, and quantile-based segmentation were applied to better understand the structure of the data.

On the visualization side, Power BI was used to build interactive dashboards that highlight:

* Global demand for different data roles
* Salary comparisons across job titles and countries
* Hiring trends over time
* Skill and education requirements
* Remote work and employment patterns
---

## Project Structure

```
GLOBAL DATA JOBS ANALYSIS/
│
├── data/
│   └── global_jobs_data.xlsx        # Dataset
│
|── power_bi/                        # Data Visualization 
|   └── datajobs_visualization.pbit
|   └── visualization.pdf
│   └── job_analysis_images/
|        └── data_tables.jpg
|        └── jobs_density.jpg
|        └── data_jobs_percent_analysis.jpg
|        └── jobs_median_salary.jpg
|        └── key_performance_indicator.jpg
|        └── quarterly_matrix.jpg
|        └── trend_analysis.jpg
|     
├── datajobs_venv/                  # Virtual environment (not tracked)
├── datajobs_analysis.ipynb         # Main analysis notebook
├── .gitignore
├── requirements.txt
├── README.md
├── LICENSE
```

---
## ⚙️ Installation & Setup

Follow these steps to run the project locally:

### 1. Clone the Repository

```bash
git clone https://github.com/Dreamy100/Global-Data-Jobs-Analysis-and-Visualization.git
cd data-jobs-eda
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

* **Windows:**

```bash
venv\Scripts\activate
```

* **Mac/Linux:**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Project

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Then navigate to the main notebook file and run all cells.

---

## Project Setup Notes

* Ensure the dataset is located inside the `data/` folder
* File paths in the notebook are configured using relative paths for portability
* All required libraries are listed in `requirements.txt`
---

## Power BI Dashboard & Visual Insights

Power BI was used as the primary visualization and business intelligence tool in this project. While Python handled statistical validation and data preparation, Power BI enabled interactive exploration, trend analysis, and decision-focused insights.

Below are the key dashboards and insights derived:

### 1. Global Job Distribution & Role Comparison

![Dashboard](power_bi/job_analysis_images/quarterly_matrix.jpg)

#### Key Insights:

* Data Engineer roles dominate hiring volume, followed by Data Analyst and Data Scientist roles
* Despite lower volume, Cloud Engineers and Machine Learning Engineers command higher salaries
* Senior roles show higher compensation but lower job counts, indicating specialization

#### Business Understanding:

* The market favors data infrastructure roles (Data Engineering)
* High-paying roles are skill-intensive and less saturated
---

### 2. Salary Comparison Across Top Countries

![Dashboard](power_bi/job_analysis_images/jobs_median_salary.jpg)

#### Key Insights:

* Senior Data Scientist ($156K) and Machine Learning Engineer ($155K) are the top-paying roles
* Followed by Senior Data Engineer and Software Engineer roles
* Entry-level roles like Data Analyst (~$90K) are significantly lower
* Countries like the USA, UK, and Germany offer higher salaries
* India shows lower salary levels, but similar role hierarchy
* Senior Data Engineer and Data Scientist roles dominate globally

#### Business Understanding:
* Compensation strongly correlates with Experience(Senior roles),Technical depth(Machine Learning,Engineering)
* Clear geographic salary disparity
* Supports global hiring cost strategies
---

### 3. Hiring Trends Over Time (2026)

![Dashboard](power_bi/job_analysis_images/trend_analysis.jpg)

#### Key Insights:

* Hiring peaks during July–September
* Hiring drops in November–December
* Trend consistent across roles

#### Business Understanding:

* Reflects seasonal hiring cycles
* End-of-year slowdown due to budget constraints
---

### 4. Skills vs Degree & Work Trends

![Dashboard](power_bi/job_analysis_images/data_jobs_percent_analysis.jpg)

#### Key Insights:

* ~33% of jobs do not require a degree
* Senior roles more likely to mention degrees
* ~87% jobs allow remote work, yet ~91% are full-time

#### Business Understanding:

* Shift toward skills-first hiring
* Remote work is normalized, but job structure remains traditional
---

### 5. Global Job Density Map

![Dashboard](power_bi/job_analysis_images/jobs_density.jpg)

#### Key Insights:

High job density in:

* North America
* Europe
* India (emerging hub)
* Lower presence in developing regions

#### Business Understanding:

* Data jobs cluster in tech-driven economies
* Emerging markets show growth potential
---

### Final Power BI Insights

* Data Engineering is the most in-demand role globally
* Senior roles command significantly higher salaries
* Strong geographic salary inequality exists
* Hiring follows seasonal patterns
* Industry is shifting toward skills over degrees
* Remote work is common, but full-time roles dominate
---

## Tech Stack

* **Python**
* **Pandas** – Data manipulation
* **NumPy** – Statistical operations
* **Matplotlib / Seaborn** – Visualization
* **Power BI** - Visualization

---

## Data Cleaning & Preparation

Key preprocessing steps performed:

* Converted `job_posted_date` to datetime format
* Converted salary columns to numeric format
* Handled missing values in salary columns
* Removed rows with missing job titles
* Created clean subsets for statistical analysis

---

## Key Analyses Performed

### 1. Salary Distribution Analysis

* Identified overall salary distribution
* Observed:

  * Mean salary ≈ **$120K**
  * Median salary ≈ **$113K**
  * Maximum salary ≈ **$920K**

 **Insight:**

* The dataset shows a **right-skewed distribution**
* A few extremely high salaries pull the average upward

---

### 2. Outlier Detection using IQR

Used Interquartile Range (IQR) to detect outliers:

* Q1 (25th percentile)
* Q3 (75th percentile)
* IQR = Q3 - Q1

Outliers defined as:

```
Lower Bound = Q1 - 1.5 * IQR
Upper Bound = Q3 + 1.5 * IQR
```

 **Insight:**

* Significant high-end salary outliers exist
* Median is a more reliable measure than mean in skewed distributions

---

### 3. Salary Band Segmentation (Quantile-Based)

Used `pd.qcut()` to divide salaries into 4 equal groups:

* Low
* Mid
* High
* Very High

 **Insight:**

* Each band contains ~25% of data
* Demonstrates balanced segmentation using quantiles

---

 **Insight:**

* Observed salary differences are **statistically significant**
* Not due to random chance

---

### 4. Variability & Distribution Analysis

Analyzed:

* Standard deviation
* Skewness
* Spread of salaries

 **Insight:**

* High standard deviation indicates wide salary variation
* Outliers significantly impact distribution

---

## Key Business Insights

* Salary distributions are **right-skewed** with high-end outliers
* Entry-level roles tend to have **compressed salary bands**
* Senior roles show **higher variability in compensation**
* Geographic location significantly impacts compensation

---

## What This Project Demonstrates

* Strong **data cleaning and wrangling skills**
* Ability to apply **statistical reasoning in real datasets**
* Understanding of **data distributions and outliers**
* Capability to extract **business insights from raw data**
* Experience with **real-world messy datasets**

---

## Final Note

This project is part of my journey to becoming a highly skilled data analyst. It focuses not just on coding, but on **thinking like an analyst — questioning data, validating assumptions, and extracting real-world insights.**

---

## License

This project is licensed under the terms of the LICENSE file included in this repository.