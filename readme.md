# 🔋 Battery Health Prediction using Machine Learning

A machine learning project to predict battery **State of Health (SoH)** and detect anomalies using NASA's Lithium-Ion Battery Aging Dataset. This project implements XGBoost regression and Isolation Forest for predictive maintenance analytics.

## 📁 Project Structure

```
battery-health-ml/
├── assets/             # Project output visualizations
├── data/               # Raw .mat telemetry files (NASA dataset)
├── models/             # Saved trained ML models (joblib)
├── notebooks/          # Jupyter notebooks for EDA and model development
├── src/                # Source code modules
├── tests/              # Unit tests
└── README.md
```

## 📊 Dataset

**NASA Lithium-Ion Battery Aging Dataset**

| File | Description |
|------|-------------|
| `B0005.mat` | Battery 5 telemetry cycles |
| `B0006.mat` | Battery 6 telemetry cycles |
| `B0007.mat` | Battery 7 telemetry cycles |
| `B0018.mat` | Battery 18 telemetry cycles |

Raw MATLAB `.mat` files loaded using `scipy.io`, containing nested battery cycle structures with charge/discharge telemetry.

---

## ⚙️ Technologies Used

| Category | Tools |
|----------|-------|
| Language | Python 3 |
| Notebooks | Jupyter Notebook |
| Data Processing | NumPy, Pandas, SciPy |
| Visualization | Matplotlib |
| Machine Learning | Scikit-learn, XGBoost |
| Anomaly Detection | Scikit-learn (Isolation Forest) |
| Model Persistence | joblib |

---

## 🔄 Workflow

### 1. Data Loading and Parsing
- Loaded `.mat` files using `scipy.io`
- Extracted nested battery cycle structures
- Parsed charge cycles, discharge cycles, and battery measurements

### 2. Battery Cycle Extraction
- Filtered discharge cycles from the dataset
- Extracted operational signals: Voltage, Current, Temperature, Discharge time, Capacity

### 3. State of Health (SoH) Calculation
SoH = (Current Capacity / Initial Capacity) × 100

- Generated degradation trends across battery cycles

### 4. Exploratory Data Analysis (EDA)
- Visualized capacity degradation and SoH decline
- Performed statistical analysis on telemetry signals
- Generated correlation heatmaps

### 5. Feature Engineering

| Feature | Description |
|---------|-------------|
| `avg_voltage` | Average discharge voltage |
| `max_voltage` | Maximum voltage |
| `min_voltage` | Minimum voltage |
| `avg_current` | Average discharge current |
| `avg_temperature` | Average temperature |
| `max_temperature` | Peak temperature |
| `discharge_duration` | Duration of discharge cycle |

### 6. ML Model Development
- **Model:** XGBoost Regressor
- **Tasks:** Battery SoH prediction, lifespan estimation, predictive maintenance
- **Evaluation Metrics:** MAE, RMSE, R² Score

### 7. Anomaly Detection
- **Algorithm:** Isolation Forest (unsupervised)
- Detects abnormal degradation and unusual battery behavior
- Identifies thermal anomalies and abnormal SoH patterns

### 8. Model Saving
- Trained models saved using `joblib`
- Processed datasets stored for future experiments

## 🔋 State of Charge (SOC) Estimation

The project was further extended to include Battery **State of Charge (SOC)** estimation using telemetry signals such as voltage, current, and temperature.

### SOC Workflow
- Extracted discharge cycle telemetry
- Generated SOC approximation curves
- Built SOC prediction models using XGBoost
- Evaluated SOC prediction performance using regression metrics

### SOC Visualizations

#### Voltage vs SOC
![Voltage vs SOC](assets/voltage_v_soc.png)

#### Actual vs Predicted SOC
![Predicted vs Actual SOC](assets/predicted_vs_actual_soc.png)

---

## 🌡️ Thermal Safety Analytics & Thermal Runaway Risk Monitoring

To simulate real-world EV battery safety analytics, thermal monitoring and thermal runaway risk analysis modules were implemented.

### Thermal Analytics Features
- Temperature instability analysis
- Thermal warning detection
- High-risk battery cycle identification
- Thermal runaway risk scoring

---

## 🚗 Extended EV Battery AI Platform

The project evolved into a broader EV battery analytics platform including:

- ✅ State of Health (SoH) Prediction
- ✅ State of Charge (SOC) Estimation
- ✅ Battery Anomaly Detection
- ✅ Thermal Safety Monitoring
- ✅ Thermal Runaway Risk Analytics
- ✅ Predictive Maintenance Workflows

---

## 📌 Advanced Project Outcomes

- Developed a multi-module EV battery analytics pipeline using NASA battery degradation datasets
- Implemented both supervised and unsupervised machine learning workflows
- Simulated industry-style battery monitoring and predictive maintenance systems
- Built thermal risk monitoring and early warning analytics for battery safety applications
- Extended the project toward Battery Management System (BMS) and automotive AI use cases

---

## 📈 Visualizations

### Battery Capacity Degradation
![Battery Capacity Degradation](assets/battery_capacity_degradation.png)

### State of Health (SoH) Over Cycles
![Battery SoH Plot](assets/battery_soh_plot.png)

### Feature Dataframe
![Feature Dataframe](assets/feature_dataframe.png)

### Correlation Heatmap
![Correlation Map](assets/corelation_map.png)

### Feature Importance
![Feature Importance](assets/feature_importance.png)

### Plot Feature Importance
![Plot Feature Importance](assets/plot_feature_importance.png)

### Model Evaluation
![Model Evaluation](assets/model_evaluation.png)

### Train / Test Split
![XY Test Train](assets/xy_test_train.png)

### Actual vs Predicted SoH
![Actual Predicted SoH](assets/actual_predicted_soh.png)

### Prediction Execution
![Y Pred Execution](assets/y_pred_execution.png)

### Isolation Forest Execution
![Isolation Forest Execution](assets/isolation_forest_execution.png)

### Battery SoH with Detected Anomalies
![Battery SoH Anomalies](assets/Battery_SoH_with_Detected_Anomalies.png)

### Temperature vs SoH Anomalies
![Temperature Battery Plot](assets/temp_battery_plot.png)

### Thermal Monitoring Visualizations

#### Thermal Risk Trend
![Thermal Risk Trend](assets/thermal_risk_trend.png)

#### Thermal Warning Detection
![Thermal Warning Detection](assets/thermal_warning_detection.png)

#### Thermal Runaway Risk Monitoring
![Thermal Runaway Risk Monitoring](assets/thermal_runaway_risk_monitoring.png)

#### High Risk Thermal Events
![High Risk Events](assets/runaway_risk_event.png)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Git

### Installation

```bash
git clone https://github.com/Ramtikka/battery-health-ml.git
cd battery-health-ml
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Run Notebooks

```bash
jupyter notebook
```

---

## 📋 Requirements
numpy
pandas
matplotlib
scikit-learn
xgboost
scipy
jupyter
joblib

---

## 📌 Key Results

- Successfully predicted battery SoH using XGBoost with high R² scores
- Identified top degradation indicators: **temperature behavior**, **voltage characteristics**, and **discharge duration**
- Isolated anomalous battery cycles using Isolation Forest for predictive maintenance

---

## 📚 References

- [NASA Battery Dataset](https://www.nasa.gov/content/prognostics-center-of-excellence-data-set-repository)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [Scikit-learn Documentation](https://scikit-learn.org/)

---

## 👤 Author

**Ramakrishna**
Data Science & ML Enthusiast
📍 Germany
🔗 [GitHub](https://github.com/Ramtikka)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
