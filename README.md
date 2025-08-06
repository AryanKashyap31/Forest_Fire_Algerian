
🔥 Algerian Forest Fires Prediction Project
This project presents a full-stack, end-to-end machine learning pipeline deployed as a web app to predict fire risk in Algerian forests. The system uses real meteorological data and the Canadian Forest Fire Weather Index System features to estimate fire occurrence, making it a practical tool for environmental monitoring and resource management.

Project Structure
1. Data Source:

The core data is from Algerian_forest_fires_dataset_UPDATE.csv, covering two regions (Bejaia & Sidi-Bel Abbes), with weather and fire indices and a target variable (Classes: fire/not fire).

2. Data Cleaning & Preparation:

Notebook: dataCleaning.ipynb

Loads, cleans, merges, and preprocesses the raw dataset.

Handles region split, removes headers and footers, drops nulls and inconsistent entries.

Converts categorical labels ("fire"/"not fire") and region info into numeric codes for modeling.

Performs exploratory data analysis (EDA), including correlation analysis.

Output: Algerian_forest_fires_cleaned_dataset.csv.

3. Model Training:

Notebook: model_Training.ipynb

Loads the clean data.

Trains a machine learning classifier (Ridge Regression, possibly for FWI or binary classification?) to predict fire occurrence, using features like Temperature, Humidity, Wind Speed, ISI, etc.

Scales features, evaluates performance, and saves the model and scaler as pickled objects for deployment (models/ridge.pkl, models/scaler.pkl).

4. Web Application:

Backend: application.py

Flask-based backend which loads the model and scaler.

Exposes two routes:

/ : Home/index page.

/predictdata : Form-based prediction endpoint. Accepts input features from web form, applies standard scaling, and outputs prediction (renders result to home.html).

Frontend:

index.html, home.html (templates with input forms and results display).

5. Requirements:

Dependencies listed in requirements.txt: Flask, numpy, pandas, scikit-learn, gunicorn.

Running Locally
Install dependencies:

bash
pip install -r requirements.txt
Train your model (optional):

Run dataCleaning.ipynb and model_Training.ipynb to re-clean and retrain, if you modify data or want to experiment.

Start the web app:

bash
python application.py
Access the UI:

Visit http://localhost:5001 in your web browser.

Features
Real Algerian wildfire dataset: Split by region, with weather and fire condition features.

Automated preprocessing: Cleans, segment, and numerically encodes all data.

Data analysis: EDA and feature correlation visualizations (see Jupyter notebooks).

ML model pipeline: Trains and persists a Ridge regression model for classification or FWI prediction.

End-to-end deployment: Intuitive web form for predictions, using Flask and HTML templates.

Easy reproducibility: All dependencies and notebooks included.
