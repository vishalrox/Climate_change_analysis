# 🌍 Climate Change Modeling using Machine Learning

A time-series–aware climate analysis project that applies **traditional machine learning models** to study the relationship between **CO₂ emissions and global temperature**, perform **scenario analysis**, and generate **future temperature projections**.

> ⚠️ This project intentionally avoids deep learning to maintain **interpretability, transparency, and scientific explainability**.

---

## 📌 Project Overview

Climate change is one of the most critical global challenges. This project analyzes historical climate data to:

- Understand long-term climate trends
- Quantify the impact of **CO₂ emissions** on temperature
- Predict future global temperature changes
- Perform **scenario-based analysis** under different CO₂ emission levels

The project emphasizes:
- Time-series–safe modeling
- Feature engineering over black-box models
- Explainable and interpretable ML outputs

---

## 📊 Dataset Description

The dataset contains historical climate observations with the following columns:

| Column Name | Description |
|------------|------------|
| Date | Observation date |
| Location | Observation location |
| Country | Country name |
| Temperature | Temperature in °C |
| CO2 Emissions | CO₂ emission level |
| Sea Level Rise | Sea level rise measurement |
| Precipitation | Rainfall data |
| Humidity | Relative humidity |
| Wind Speed | Average wind speed |

All data is processed chronologically to preserve **time-series integrity**.

---

## 🔍 Exploratory Data Analysis (EDA)

Key visualizations and analyses include:

- Global **Temperature vs CO₂** trend (dual-axis plot)
- Distribution of CO₂ emissions
- Top 10 CO₂ emitting countries
- Location-specific CO₂ time-series
- Correlation heatmap of climate variables
- Scatter plot showing CO₂–Temperature relationship

📈 **Key Insight:**  
Temperature shows a strong positive correlation with CO₂ emissions and sea level rise.

---

## ⚙️ Data Preprocessing

- Converted raw data into **global monthly averages**
- Removed missing and inconsistent values
- Ensured chronological ordering to prevent data leakage
- Retained only relevant numerical features for modeling

---

## 🧠 Feature Engineering

To capture temporal behavior without deep learning, the following features were engineered:

- `CO2_Lag1` → Previous month’s CO₂ emissions
- `Temp_Lag1` → Previous month’s temperature
- `Temp_Rolling_12` → 12-month rolling average temperature

These features allow traditional ML models to learn delayed and seasonal effects.

---

## 🤖 Models Used

The following **traditional regression models** were trained and compared:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

### Training Strategy
- **Time-series split** (80% train, 20% test)
- Feature scaling applied only for Linear Regression
- Model selection based on **lowest RMSE**

---

## 📐 Model Evaluation

Evaluation metrics used:

- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)
- **R² Score**

Diagnostic plots:
- Actual vs Predicted temperature
- Residual plots
- Feature importance (tree-based models)

---

## 🔮 Future Temperature Projections

- Generated **24-month future temperature forecasts**
- CO₂ emissions extrapolated using historical trends
- Other climate variables fixed at long-term averages

> These forecasts represent **scenario-based estimates**, not deterministic predictions.

---

## 🔁 Scenario Analysis (CO₂ Impact)

Three scenarios were simulated using the latest climate state:

- **Low Emission:** −50 units CO₂
- **Baseline:** Current conditions
- **High Emission:** +50 units CO₂

📌 **Finding:**  
Increasing CO₂ emissions results in a measurable rise in predicted global temperature.

A zoomed Y-axis visualization highlights marginal differences clearly.

---

## 🧪 Key Results & Insights

- CO₂ emissions are the **dominant driver** of temperature change
- Lagged and rolling features significantly improve accuracy
- Traditional ML models are effective when combined with proper feature engineering
- Scenario analysis provides **interpretable and actionable insights**

---

## ⚠️ Limitations

- Assumes linear CO₂ trends
- Does not explicitly model extreme climate events
- Climate system complexity introduces uncertainty
- Predictions should be treated as **estimates**, not exact forecasts

---

## 🚀 Future Improvements

- Regional or country-level modeling
- Integration with IPCC benchmark data
- Interactive dashboard (Streamlit)
- Policy-driven emission scenarios

---

## 🧾 How to Run the Project

```bash
git clone https://github.com/vishalrox/Climate_change_analysis.git
cd Climate_change_analysis
pip install -r requirements.txt
jupyter notebook

