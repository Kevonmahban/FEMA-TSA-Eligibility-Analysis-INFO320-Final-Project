
# FEMA TSA Eligibility Analysis

## Overview
This project investigates the FEMA Transitional Sheltering Assistance (TSA) program, with the objective of identifying key patterns in usage, evaluating disaster impact, and predicting TSA eligibility through machine learning. The analysis supports FEMA’s mission to improve response effectiveness during disaster recovery.

## Repository Contents
- `finalproject.ipynb`: Main notebook containing descriptive statistics, machine learning models, and performance evaluation.
- `KeyAnalysisTasks.ipynb - Colab.pdf`: Supplementary notebook output with exploratory data analysis and key metrics used for insight development.
- `INFO_320_FEMA_Project.pdf`: Full project brief outlining analysis requirements, model expectations, and ethical components.
- *(Dataset is external; see below for link.)*

## Dataset
The analysis uses FEMA’s publicly available dataset:
- [Individual Assistance Housing Registrants Large Disasters CSV](https://www.fema.gov/about/reports-and-data/openfema/IndividualAssistanceHousingRegistrantsLargeDisasters.csv)

## Key Analysis Tasks

### Descriptive Statistics (Python)
Based on the Colab analysis (`KeyAnalysisTasks.ipynb`) and final notebook:
- **TSA Usage by State**: Highest in Florida, Puerto Rico, and Texas.
- **Income Differences**:
  - TSA users: ~$43,588
  - Non-TSA users: ~$53,006
- **Household Composition**:
  - TSA users: avg. 2.22
  - Non-TSA users: avg. 2.28
- **Water Level**:
  - TSA-approved: 287,274 records
  - Non-approved: 455,804 records
- **Repair Costs**:
  - TSA users: ~$587
  - Non-TSA users: ~$228
- **Damage Breakdown**:
  - Roof Damage: higher average for TSA-approved cases (6.0% vs. 2.1%)
  - Foundation Damage: slightly higher in TSA cases (0.79% vs. 0.41%)
- **Residence Type Counts**: Majority from House/Duplex (458,000+) and Apartments.

### Disaster-Specific Analysis
For each disaster, total TSA cases and average repair costs were computed:

| Disaster               | Number | TSA Cases | Avg. Repair Cost |
|------------------------|--------|-----------|------------------|
| Hurricane Harvey       | 4332   | 43,830    | $1,019.28        |
| Hurricane Irma         | 4337   | 102,597   | $71.99           |
| Hurricane Maria        | 4339   | 120,662   | $493.96          |
| Hurricane Laura        | 4559   | 0         | $420.98          |
| Hurricane Ida          | 4611   | 18,467    | $456.41          |
| Texas Winter Storm     | 4586   | Data sample: 48,690 rows | $182.71 |
| Hurricane Florence     | 4393   | 739       | $516.41          |
| Hurricane Michael      | 4399   | 979       | $588.99          |

### Predictive Modeling
Three supervised models were trained to predict `tsaEligible` using features like income, household size, residence type, damage, and repair amount:
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**
- **Random Forest**

Each model was evaluated using:
- Accuracy
- Precision
- Confusion Matrix (TP, TN, FP, FN)
- Justification and tuning based on Occam's Razor

### Ethics of AI in Disaster Relief
The project includes a discussion on the appropriate role of AI in emergency contexts, considering its use for recommendations versus decision-making. It reflects on transparency, bias risks, and the importance of human oversight.

## Requirements
- Python 3.x
- Required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

## How to Run
1. Download or clone the repository.
2. Open `finalproject.ipynb` in Jupyter Notebook or Google Colab.
3. Ensure access to the FEMA CSV dataset.
4. Run cells sequentially for full analysis and model outputs.

## Notes
- This project includes both exploratory and predictive elements.
- Power BI dashboard components were completed separately and are not part of this repository.
