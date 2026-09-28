# 🌾 Geospatial Data Visualization using Amazon SageMaker

An end-to-end cloud-based agricultural analytics platform that combines **geospatial visualization**, **machine learning**, and **interactive dashboards** to analyze crop distribution and soil health across India.

---

## 📌 Overview

This project ingests an agricultural dataset containing crop types, geographic coordinates, and soil nutrient parameters (NPK & pH) from **Amazon S3**, processes it in an **Amazon SageMaker** JupyterLab environment, applies supervised and unsupervised machine learning models, and renders the results as interactive browser-based maps using **Folium** and **Leaflet.js**.

A **Streamlit** web application packages the key visualizations into a navigable dashboard, publicly accessible via Localtunnel.

---

## ✨ Features

- 🗺️ **Crop Distribution Map** — Color-coded interactive markers for 10 crop types with a client-side JavaScript dropdown filter
- 🔥 **Soil Nutrient Heat Maps** — Individual and composite heat maps for Nitrogen, Phosphorous, Potassium, and pH using data-driven quintile gradients
- 🤖 **Crop Location Prediction** — Random Forest Regressor predicts geographic coordinates from soil parameters; actual vs. predicted locations visualized with connecting lines
- 📍 **Regional Clustering** — K-Means groups crop types into 5 geographic agricultural zones with centroid markers
- 📊 **Streamlit Dashboard** — Two-view web app (Location Prediction + Crop Clusters) with sidebar navigation, publicly tunneled via Localtunnel

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Cloud Storage | Amazon S3 |
| ML Environment | Amazon SageMaker (JupyterLab) |
| Language | Python 3.8+ |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn (RandomForestRegressor, KMeans) |
| Visualization | Folium, Leaflet.js |
| Web App | Streamlit, streamlit-folium |
| Tunneling | Localtunnel |

---

## 📊 Dataset

The dataset (`CropDataset-Enhanced.csv`) contains **730 records** across **23 columns**:

| Column | Description |
|---|---|
| `Address` | Location name |
| `Latitude`, `Longitude` | Geographic coordinates |
| `Region`, `Country` | Administrative region |
| `Crop` | Crop type(s) grown at the location |
| `Nitrogen - High/Medium/Low` | Soil nitrogen level distribution (%) |
| `Phosphorous - High/Medium/Low` | Soil phosphorous level distribution (%) |
| `Potassium - High/Medium/Low` | Soil potassium level distribution (%) |
| `pH - Acidic/Neutral/Alkaline` | Soil pH classification distribution (%) |

---

## 🧠 ML Models

### Random Forest Regressor
- **Task:** Predict geographic coordinates (latitude & longitude) from soil parameters
- **Features:** NPK Score, pH Value, and processed soil columns
- **Validation:** 5-fold cross-validation with MSE and R² metrics
- **Library:** `sklearn.ensemble.RandomForestRegressor`

### K-Means Clustering
- **Task:** Group crop types into geographic agricultural zones
- **Input:** Average latitude & longitude per unique crop type
- **Clusters:** 5 (configurable)
- **Library:** `sklearn.cluster.KMeans`

---

## 🗺️ Visualizations

| Map | Description |
|---|---|
| Crop Distribution | Color-coded markers with JS dropdown filter |
| Nitrogen Heat Map | Intensity map of nitrogen levels across regions |
| Phosphorous Heat Map | Intensity map of phosphorous levels |
| Potassium Heat Map | Intensity map of potassium levels |
| NPK Heat Map | Composite soil fertility heat map |
| pH Heat Map | Soil acidity/alkalinity distribution |
| Prediction Map | Actual (blue) vs. predicted (red) locations with connecting lines |
| Cluster Map | 5 geographic crop clusters with centroid star markers |
