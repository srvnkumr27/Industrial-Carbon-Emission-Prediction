# 🌱 Industrial Carbon Emission Prediction

An end-to-end **Machine Learning project** that predicts industrial **CO₂ emissions** using energy consumption and operational data from the steel industry.

The project performs data preprocessing, exploratory data analysis, visualization, feature engineering, multiple regression models, model evaluation, feature importance analysis, and real-time carbon emission prediction.

---

## 📌 Project Overview

Industrial production consumes large amounts of energy and can generate significant carbon emissions.

This project uses Machine Learning to learn the relationship between industrial energy consumption and CO₂ emissions and predict the expected carbon emissions for new operational conditions.

### 🎯 Objective

> Predict **CO₂ emissions (`CO2(tCO2)`)** based on industrial energy consumption, power factors, reactive power, load type, and operational information.

---

## 🚀 Project Workflow

```text
                    Steel Industry Dataset
                             │
                             ▼
                    Data Preprocessing
                             │
                             ▼
                 Exploratory Data Analysis
                             │
                             ▼
                    Feature Engineering
                             │
                             ▼
                     Train/Test Split
                             │
                             ▼
                    Machine Learning
                             │
             ┌───────────────┼───────────────┐
             ▼               ▼               ▼
       Linear Regression  Decision Tree  Random Forest
             │               │               │
             └───────────────┼───────────────┘
                             ▼
                    Gradient Boosting
                             │
                             ▼
                     Model Comparison
                             │
                             ▼
                     Best Model Selection
                             │
                             ▼
                  CO₂ Emission Prediction
                             │
                             ▼
                    Model Serialization
                             │
                             ▼
                    Real-Time Prediction
```

---

## 📊 Dataset

The project uses a **Steel Industry Energy Consumption dataset**.

The dataset contains industrial energy and operational measurements recorded at regular time intervals.

### Dataset Features

| Feature | Description |
|---|---|
| `Date_Time` | Date and time of observation |
| `Usage_kWh` | Energy consumption in kWh |
| `Lagging_Current_Reactive.Power_kVarh` | Lagging reactive power |
| `Leading_Current_Reactive_Power_kVarh` | Leading reactive power |
| `CO2(tCO2)` | Target CO₂ emission |
| `Lagging_Current_Power_Factor` | Lagging power factor |
| `Leading_Current_Power_Factor` | Leading power factor |
| `NSM` | Number of seconds from midnight |
| `WeekStatus` | Weekday or weekend status |
| `Day_Of_Week` | Day of the week |
| `Load_Type` | Industrial load category |

### 🎯 Target Variable

```text
CO2(tCO2)
```

---

## 🧠 Machine Learning Models

The project compares multiple regression algorithms:

### 1. Linear Regression

Used as a baseline regression model.

### 2. Decision Tree Regressor

Captures nonlinear relationships between industrial features and CO₂ emissions.

### 3. Random Forest Regressor

Uses multiple decision trees to improve prediction performance and reduce overfitting.

### 4. Gradient Boosting Regressor

Builds models sequentially to improve prediction accuracy.

The best-performing model is automatically selected based on **R² Score**.

---

## 📈 Exploratory Data Analysis

The project generates several visualizations to understand the dataset.

### Visualizations Included

- CO₂ emissions over time
- Energy consumption over time
- Energy consumption vs CO₂ emissions
- CO₂ emission distribution
- Correlation heatmap
- CO₂ emissions by load type
- CO₂ emissions by day of week
- Average CO₂ emissions by hour
- Model performance comparison
- Actual vs predicted CO₂
- Residual analysis
- Prediction error distribution
- Feature importance

---

## 📏 Model Evaluation

The following metrics are used:

### Mean Absolute Error — MAE

Measures the average absolute difference between actual and predicted emissions.

```text
MAE = average(|Actual - Predicted|)
```

Lower MAE indicates better performance.

### Root Mean Squared Error — RMSE

Penalizes larger prediction errors.

```text
RMSE = √MSE
```

Lower RMSE indicates better performance.

### R² Score

Measures how well the model explains the variation in CO₂ emissions.

```text
R² → closer to 1 = better model
```

---

## 🔍 Feature Importance

For tree-based models, feature importance is extracted to understand which variables contribute most to CO₂ predictions.

Example:

```text
Energy Consumption
        ↓
Power Factor
        ↓
Reactive Power
        ↓
Load Type
        ↓
Operational Features
```

This helps make the Machine Learning model more interpretable.

---

## ⚡ Real-Time Prediction

The project includes a prediction function that accepts new industrial operating conditions.

Example:

```python
prediction = predict_carbon_emission(
    usage_kwh=300,
    lagging_reactive=100,
    leading_reactive=20,
    lagging_power_factor=80,
    leading_power_factor=95,
    nsm=36000,
    week_status="Weekday",
    day_of_week="Monday",
    load_type="Medium_Load"
)

print(prediction)
```

The model returns the predicted CO₂ emissions.

---

## 🛠️ Technologies Used

### Programming Language

- Python

### Data Processing

- Pandas
- NumPy

### Data Visualization

- Matplotlib
- Seaborn

### Machine Learning

- Scikit-learn

### Model Saving

- Joblib

### Development Environment

- Jupyter Notebook
- VS Code

### Future Deployment

- Streamlit

---

## 📂 Project Structure

```text
industrial-carbon-emission-prediction/
│
├── data/
│   └── Steel_industry_data.csv
│
├── notebooks/
│   └── carbon_emission_prediction.ipynb
│
├── src/
│   └── carbon_emission_prediction.py
│
├── carbon_emission_model.pkl
│
├── model_comparison.csv
│
├── prediction_results.csv
│
├── requirements.txt
│
└── README.md
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/industrial-carbon-emission-prediction.git
```

Move into the project directory:

```bash
cd industrial-carbon-emission-prediction
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

---

## 📦 Requirements

Create a `requirements.txt` file containing:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
```

---

## ▶️ Running the Project

Make sure the dataset is located in the project directory.

Run:

```bash
python src/carbon_emission_prediction.py
```

Or open the Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
notebooks/carbon_emission_prediction.ipynb
```

---

## 💾 Saved Model

After training, the best-performing model is saved as:

```text
carbon_emission_model.pkl
```

The model can later be loaded using:

```python
import joblib

model = joblib.load("carbon_emission_model.pkl")
```

---

## 🔮 Future Improvements

The project can be extended into a complete **AI-based Carbon Monitoring System**.

### Planned Features

- [ ] Streamlit dashboard
- [ ] Real-time CO₂ prediction
- [ ] Interactive energy monitoring
- [ ] Carbon emission alerts
- [ ] Historical emission trends
- [ ] SHAP-based explainability
- [ ] Energy optimization recommendations
- [ ] Carbon reduction recommendations
- [ ] Cloud deployment
- [ ] API-based prediction service

---

## 🌍 Real-World Application

This system can be adapted for industrial environments to:

- Monitor energy consumption
- Estimate carbon emissions
- Identify high-emission operating conditions
- Compare production periods
- Support sustainability decisions
- Identify opportunities for reducing energy consumption

---

## 📊 Future System Architecture

```text
Industrial Sensors / Data
          │
          ▼
    Data Collection
          │
          ▼
    Machine Learning
          │
     ┌────┴─────┐
     ▼          ▼
CO₂ Prediction  Energy Analysis
     │          │
     └────┬─────┘
          ▼
   Carbon Dashboard
          │
          ▼
 AI Optimization Recommendations
```

---

## 👨‍💻 Author

**M. Sravan Kumar Varma**

B.Tech — Computer Science Engineering  
Artificial Intelligence & Machine Learning

---

## ⭐ Project Goal

The goal of this project is to demonstrate how Machine Learning can be applied to **industrial sustainability and carbon emission monitoring**.

If you find this project useful, consider giving the repository a ⭐.

---

## 📜 License

This project is intended for educational and research purposes.
