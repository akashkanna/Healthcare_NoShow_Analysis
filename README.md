# Healthcare Telemedicine Project

## Overview

This repository contains the Healthcare Telemedicine Project, a data analysis and exploratory study of patient appointment behavior using the Kaggle healthcare dataset. The goal is to uncover patterns around appointment attendance, patient demographics, medical conditions, and waiting time between scheduling and appointment date.

The project includes data preparation, exploratory data analysis (EDA), feature engineering, statistical tests, and visualization assets to support clear insights for healthcare operations and telemedicine planning.

> A preview dashboard for this project is available at: https://health-eda.onrender.com/

## Dataset

The dataset is stored in `data/KaggleV2-May-2016.csv` and contains appointment records with the following columns:

- `PatientId`: Unique ID for the patient.
- `AppointmentID`: Unique ID for the appointment.
- `Gender`: Patient gender (`M` or `F`).
- `ScheduledDay`: Date and time when the appointment was scheduled.
- `AppointmentDay`: Date of the appointment.
- `Age`: Patient age.
- `Neighbourhood`: Clinic neighborhood.
- `Scholarship`: Whether the patient is enrolled in Brazil's Bolsa Família program.
- `Hipertension`: Whether the patient has hypertension.
- `Diabetes`: Whether the patient has diabetes.
- `Alcoholism`: Whether the patient has an alcoholism problem.
- `Handcap`: Whether the patient has a handicap.
- `SMS_received`: Whether the patient received an SMS reminder.
- `No-show`: Whether the patient missed the appointment (`Yes` or `No`).

## Key Questions Addressed

- What patient attributes correlate with missed appointments?
- How does waiting time between scheduling and appointment affect attendance?
- Are there demographic patterns in no-shows, such as age or gender?
- Which neighborhoods have the highest appointment absenteeism?
- How do medical conditions such as hypertension, diabetes, and alcoholism relate to attendance?

## Repository Structure

- `data/` - Raw dataset files used for analysis.
- `notebooks/` - Jupyter notebook(s) containing the exploration and model work.
- `scripts/` - Python script(s) for automated EDA and preprocessing.
- `outputs/` - Generated charts, graphs, and analysis export files.
- `visualizations/` - Final visualization assets produced during the project.
- `presentation/` - Slide deck or presentation files summarizing results.
- `ieee_report/` - Report and documentation for academic or project submissions.
- `README.md` - Project documentation and usage instructions.

## Main Files

- `scripts/app.py` - Main Python script that loads the dataset, performs EDA, feature engineering, and generates visualizations for waiting time, age distribution, gender distribution, and appointment attendance.
- `notebooks/Team_1_Project_complete.ipynb` - Colab notebook with step-by-step analysis and code cells for the full project workflow.

## Usage

1. Install required Python packages if not already available. Common packages used in this project include:
   - `pandas`
   - `numpy`
   - `seaborn`
   - `matplotlib`
   - `scipy`

2. Run the main analysis script from the project root:

```bash
python scripts/app.py
```

3. Open the notebook to review the interactive analysis:

```bash
jupyter notebook notebooks/Team_1_Project_complete.ipynb
```

## Analysis Highlights

The project workflow includes:

- Loading and validating the appointment dataset.
- Converting scheduled and appointment dates to datetime format.
- Creating a new `Waiting_Time` feature representing days between scheduling and appointment.
- Handling negative waiting times and ensuring valid transformation inputs.
- Analyzing outliers in age and waiting time.
- Comparing raw and transformed distributions using logarithmic and Box-Cox transformations.
- Examining no-show behavior with univariate and bivariate visualizations.
- Comparing appointment attendance across gender, age, and health conditions.

## Visualizations

The repository contains multiple visualization outputs, including:

- `visualizations/age_distribution.png`
- `visualizations/age_outlier_detection.png`
- `visualizations/age_vs_no_show_boxplot.png`
- `visualizations/appointment_attendance_pie.png`
- `visualizations/correlation_heatmap.png`
- `visualizations/no_show_distribution.png`
- `visualizations/waiting_time_transformations.png`

These charts support the analysis by showing distribution trends, correlations, and appointment attendance behavior.

## Notes

- This project is designed for exploratory analysis rather than production deployment.
- The dataset covers a real-world patient appointment scenario and is useful for identifying operational improvements in telemedicine scheduling.
- The repository is structured to keep raw data, code, and visual results separate for better reproducibility.

## Contact

For additional details, open the notebook or review the `ieee_report` folder for the written project documentation.
