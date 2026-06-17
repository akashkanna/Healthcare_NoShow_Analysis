# Healthcare Telemedicine Project — README

## Overview

This repository contains the Healthcare Telemedicine Project: a reproducible exploratory data analysis (EDA) and visualization dashboard built from the Kaggle appointment dataset (stored in `data/`). The analysis explores drivers of appointment attendance (no-shows), the effect of waiting time, demographic and medical-condition correlations, and neighborhood-level patterns.

A live preview of the interactive dashboard is hosted at: [Healthcare EDA Dashboard](https://health-eda.onrender.com/)

This repo contains two primary ways to use the work:
- Run the analysis and plots locally (scripts and notebooks).
- Launch the interactive Streamlit dashboard found in `WebSiteCode/` (recommended for exploration and sharing).

## Repository structure (summary)

- `data/` — raw dataset: `KaggleV2-May-2016.csv`.
- `notebooks/` — exploratory notebook(s): `Team_1_Project_complete.ipynb`.
- `scripts/` — analysis scripts (non-interactive), e.g. `scripts/app.py`.
- `WebSiteCode/` — Streamlit app (multi-page) used for the hosted dashboard.
  - `WebSiteCode/app.py` — Streamlit app entrypoint.
  - `WebSiteCode/pages/` — multipage views (EDA, ML, transformation, reports, etc.).
  - `WebSiteCode/utils/` — helper modules used by the app (`data_loader.py`, `analysis.py`, `ml.py`, etc.).
  - `WebSiteCode/requirements.txt` — packages required to run the Streamlit site.
- `visualizations/` — exported static figures (PNG) created by scripts/notebooks.
- `outputs/` — generated data outputs and artifacts.
- `ieee_report/` — written report and project documentation.

## What the dashboard and code do

- Load and validate the appointment dataset.
- Convert `ScheduledDay` and `AppointmentDay` to datetimes and compute `Waiting_Time` (days between scheduling and appointment).
- Clean and transform data (handle invalid/negative waiting times, outliers in `Age`, and categorical encoding).
- Produce EDA visualizations: distributions, correlation heatmaps, no-show comparisons, neighborhood summaries.
- Provide simple ML experiments to predict no-shows and show model metrics (in the `machine_learning` page).

## Quickstart — Local (recommended)

1. Install Python 3.8+ and create a virtual environment.

```bash
python -m venv .venv
# Windows PowerShell
.venv\Scripts\Activate.ps1
# or Command Prompt
.venv\Scripts\activate.bat
```

2. Install dependencies for the Streamlit app (from `WebSiteCode`):

```bash
pip install -r WebSiteCode/requirements.txt
```

3. Run the Streamlit dashboard locally:

```bash
streamlit run WebSiteCode/app.py
```

The app serves at `http://localhost:8501` by default. Use `--server.port` to change the port.

4. (Optional) Run the non-interactive analysis script used for producing static visualizations and outputs:

```bash
python scripts/app.py
```

5. Open the notebook for step-by-step analysis and reproducibility:

```bash
jupyter notebook notebooks/Team_1_Project_complete.ipynb
```

## Running with Docker (optional)

If you prefer Docker, create a simple Dockerfile around the `WebSiteCode` folder and expose port 8501. Example commands:

```bash
docker build -t health-eda -f WebSiteCode/Dockerfile .
docker run -p 8501:8501 health-eda
```

(No official Dockerfile is included; you can create one based on Python slim images and `pip install -r requirements.txt`.)

## Deployment / Hosted instance

The interactive dashboard is deployed and available at: [Healthcare EDA Dashboard](https://health-eda.onrender.com/)

If you deploy to Render, Heroku, or another PaaS, typical steps are:

- Point the service to the `WebSiteCode/` directory (or copy its contents) and set the start command to: `streamlit run app.py --server.port $PORT`.
- Ensure the `requirements.txt` is used to install dependencies.
- Configure environment variables and storage (if using persistent outputs).

## Notes on data and privacy

- The dataset used for analysis is a public Kaggle CSV (`data/KaggleV2-May-2016.csv`). Treat any real patient data with appropriate privacy controls in production.
- This project is for exploratory analysis and teaching purposes — not for clinical decision making.

## Troubleshooting

- If Streamlit fails to start: verify Python and `pip` in the active environment and confirm packages installed from `WebSiteCode/requirements.txt`.
- If data fails to load: confirm `data/KaggleV2-May-2016.csv` exists and is readable.
- To increase logging: run Streamlit with `--logger.level=debug`.

## Contributing

- Fixes, improvements, and additional visualizations are welcome. Please open an issue or submit a pull request.
- For changes to the deployed app, update `WebSiteCode/` files and redeploy to your hosting provider.

## Contact

Questions or requests: open an issue in this repo or contact the project owner listed in `ieee_report`.

---
Updated README to include full run and deployment instructions and a link to the hosted dashboard.
