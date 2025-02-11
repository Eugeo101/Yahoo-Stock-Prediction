# Yahoo Stock Prediction 📈💰  

This project focuses on **time-series forecasting** of Yahoo stock prices using multiple models, including **Naive Forecasting, SARIMA, Facebook Prophet, and XGBoost**. The dataset contains stock price data with **daily frequency** and spans multiple years. The project includes **EDA, preprocessing, model evaluation, and future predictions** based on the best-performing model.

---

## 📝 Problem Statement  
The goal is to predict **daily stock prices** based on historical **Open, High, Low, Close, Adjusted Close, and Volume** data, while accounting for **yearly seasonality** and detecting trends.

---

## 🔍 Steps Followed  

### 1️⃣ Data Understanding  
- **Features:**  
  - **Close**: Closing price of the stock.  
  - **Open**: Opening price of the stock.  
  - **High**: Highest price reached during the day.  
  - **Low**: Lowest price during the day.  
  - **Adj Close**: Adjusted closing price accounting for dividends/splits.  
  - **Volume**: Number of shares traded.

- **Seasonality & Trend Analysis:**  
  - The stock data exhibits **linear yearly seasonality** and a **linear trend** over time.  
  - Applied **rolling averages** and **seasonal decomposition** to visualize trends and patterns.

---

### 2️⃣ Exploratory Data Analysis (EDA)  
- **Visualized stock price trends over time** to understand patterns.  
- Applied **seasonal decomposition** to confirm yearly seasonality and trend.  
- **Detected and handled missing values** using forward fill and backward fill.

---

### 3️⃣ Data Preprocessing  
- **Handled missing values** by forward-filling data and other techniques where necessary.  
- **Differencing applied** remove trend & seasonality components before modeling.  
- **Normalized features** StandarScaler.  

---

### 4️⃣ Model Building and Evaluation  

#### Baseline Model:  
- **Naive Forecasting** (simple persistence model for comparison).

#### Advanced Models:  
- **Statistical Models:**  
  - **SARIMA**: Configured for daily forecasting (`p=d=q=1`) to capture seasonal effects.  

- **Facebook Prophet:**  
  - Used **yearly seasonality** (`yearly_seasonality=True`) to model stock price variations.  
  - Plotted seasonal components using `plot_components()`.  

- **Machine Learning Model:**  
  - **XGBoost:** Fine-tuned hyperparameters for optimal stock price prediction.  

#### Cross-Validation:  
- **TimeSeriesSplit** used for model validation to ensure correct handling of time-dependent data.

---

### 5️⃣ Results  

| **Model**             | **Yearly MAPE (%)** | **Yearly MAE** | **Daily MAPE (%)** | **Daily MAE** |
|----------------------|-------------------|---------------|------------------|---------------|
| Naive Forecasting    | 10.49%            | 353           | 0.7%             | 23            |
| SARIMA              | -                 | -             | 9.5%             | 325           |
| Facebook Prophet    | -                 | -             | 0.83%            | 27.75         |
| XGBoost             | -                 | -             | 2.01%            | 68            |

#### Best Model:  
- **Facebook Prophet** provided the most accurate daily forecast with **MAPE = 0.83%** and **MAE = 27.75**.

---

### 6️⃣ Future Predictions  
- Used **Facebook Prophet** for making **future stock price predictions** based on historical patterns.

---

### 7️⃣ Visualizations  
- **Facebook Prophet Plots:**  
  - Displayed yearly seasonal trends using `plot_components()`.  
- **SARIMA Residual Analysis** to check model assumptions.  
- **Stock price movement over time** using Matplotlib & Seaborn.
