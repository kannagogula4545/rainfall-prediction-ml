# 🌧️ Rainfall Prediction Using Machine Learning & Statistical Techniques

> A comparative study of time-series forecasting models (LSTM, GRU, ARIMA, SARIMA, Exponential Smoothing) on historical rainfall data from the Anand/Ahmedabad region, India.

---

## 📌 Project Overview

Accurate rainfall forecasting is critical for agriculture, water resource management, and disaster prevention. This project analyzes **30 years of historical rainfall data (1991–2021)** collected from the Meteorological Centre, Ahmedabad (IMD), and benchmarks multiple ML and statistical models to identify the best performer.

**Key Goal:** Compare LSTM, GRU, ARIMA, SARIMA, and Exponential Smoothing models and determine which produces the most accurate monthly rainfall forecasts.

---

## 🏆 Results Summary

| Model | MAE | MSE | RMSE |
|---|---|---|---|
| **LSTM** | **0.0604** | **0.0089** | **0.0944** |
| GRU | 0.0500 | 0.0100 | 0.1040 |
| Auto SARIMA | 1.4995 | 5.6504 | 2.3770 |
| Triple Exponential | 1.5500 | 7.88 | 2.8100 |
| SARIMA | 1.6604 | 10.3901 | 3.2233 |
| Double Exponential | 1.9900 | 18.38 | 4.2900 |
| ARIMA | 3.0396 | 15.3798 | 3.9217 |
| Auto ARIMA | 3.9205 | 29.99 | 5.4766 |

✅ **Winner: LSTM** — lowest error across all three metrics. Deep learning models (LSTM, GRU) significantly outperformed all statistical models.

---

## 📁 Project Structure

```
rainfall-prediction/
│
├── implementation.ipynb        # Main notebook — all models implemented here
├── Rainfall_datafile.csv       # Dataset (IMD, Anand city, 1991–2021)
├── README.md
│
├── models/
│   ├── arima_model.py
│   ├── sarima_model.py
│   ├── exponential_smoothing.py
│   ├── lstm_model.py
│   └── gru_model.py
│
└── outputs/
    ├── arima_predictions.png
    ├── sarima_predictions.png
    ├── lstm_predictions.png
    ├── gru_predictions.png
    └── model_comparison.png
```

---

## 🗃️ Dataset

- **Source:** Meteorological Centre, Ahmedabad (India Meteorological Department)
- **Region:** Anand City, Gujarat, India
- **Period:** 1991 – 2021
- **Feature:** Daily Rainfall in mm (RF)
- **Columns:** YEAR, MONTH, DATE, RF

Missing values were handled using linear interpolation and model-based estimation for longer gaps.

---

## ⚙️ Models Used

### Statistical Models
- **ARIMA** — AutoRegressive Integrated Moving Average
- **Auto ARIMA** — Automated parameter selection
- **SARIMA** — Seasonal ARIMA (handles cyclic rainfall patterns)
- **Auto SARIMA**
- **Double Exponential Smoothing** — Trend-based smoothing
- **Triple Exponential Smoothing** — Trend + seasonality

### Deep Learning Models
- **LSTM** (Long Short-Term Memory) — Captures long-term temporal dependencies
- **GRU** (Gated Recurrent Unit) — Lighter and faster than LSTM, comparable accuracy

---

## 🔧 Preprocessing Steps

1. Removed whitespace and formatted column names
2. Converted missing values to NaN
3. Filled short gaps using **linear interpolation**
4. Filled long missing periods using **model-based estimation**
5. Combined YEAR/MONTH/DATE into a single DateTime index
6. Retained only the Rainfall (mm) feature for time-series modeling

---

## 📊 Evaluation Metrics

- **MAE** (Mean Absolute Error) — Average deviation from actual values
- **MSE** (Mean Squared Error) — Penalizes large errors more heavily
- **RMSE** (Root Mean Squared Error) — Error in the same unit as rainfall (mm)

Lower values = better accuracy.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| Anaconda / Jupyter Notebook | Development environment |
| NumPy, Pandas | Data preprocessing |
| Matplotlib, Seaborn | Visualization |
| Scikit-learn | Evaluation metrics |
| TensorFlow / Keras | LSTM & GRU models |
| statsmodels | ARIMA, SARIMA, Exponential Smoothing |

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/rainfall-prediction.git
cd rainfall-prediction

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow statsmodels pmdarima

# 3. Launch Jupyter Notebook
jupyter notebook implementation.ipynb
```

---

## 📈 Key Findings

- Deep learning models (LSTM, GRU) dramatically outperformed all statistical models
- LSTM achieved the highest accuracy with MAE of just 0.0604
- GRU was slightly less accurate than LSTM but trains faster, making it a good trade-off
- SARIMA was the best statistical model due to its ability to capture seasonal patterns
- Standard ARIMA struggled with the highly seasonal and non-linear nature of rainfall data

---

## ⚠️ Limitations

- Only rainfall (mm) was used — no temperature, humidity, or wind data
- Monthly predictions only, not daily or real-time
- Dataset had significant missing periods requiring estimation
- Deep learning models need more data for even higher generalization

---

## 🔭 Future Work

- Incorporate additional weather parameters (temperature, humidity, wind speed)
- Build a real-time forecasting system using live weather APIs (OpenWeatherMap)
- Deploy as a web/mobile application
- Explore Bi-LSTM, CNN-LSTM, or Transformer-based architectures

---

## 👨‍💻 Developer

**Gogula Hari Karunakar**  
B.Tech CSE – AI & Data Science  
PIET, Parul University, Vadodara

**Guide:** Rasna Nikunjkumar Patel, Assistant Professor  
**Institution:** PIET, Parul University, Vadodara  
**Department:** CSE – AI & Data Science

---

## 📄 License

This project was developed as a B.Tech final year project (2025) at Parul University. For academic use only.
