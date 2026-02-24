![cover](cover.png)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit_Learn-orange)
![Library](https://img.shields.io/badge/Library-TensorFlow-red)
![Status](https://img.shields.io/badge/Status-Complete-green)

## ⋆‧°𓏲ּ𝄢 Project Overview

This project analyzes the Philippine Stock Market to predict future price trends using advanced machine learning algorithms. While most investment strategies locally rely on fundamental analysis or traditional econometric models, there is a notable gap in applying machine learning to the Philippine market. 

Traditional trading logic can be highly volatile and subjective. By developing predictive models, we aim to help investors make informed, data-driven decisions. We applied three distinct algorithms, **Linear Regression (LR)**, **Support Vector Machine (SVM)**, and **Long Short-Term Memory (LSTM)**, to evaluate which provides the highest predictive accuracy for local equities.

## ⋆‧°𓏲ּ𝄢 The Dataset

We utilized historical market data for the **Philippine Stock Exchange (PSE)** and the **Philippine Stock Exchange Index (PSEi)** spanning a decade, from **October 13, 2014, to October 11, 2024**. 

The dataset features key daily trading attributes:
* **Price (Close)**
* **Open, High, and Low Prices**
* **Trading Volume**
* **Change %**
These indicators were processed and sequenced to train our models to forecast stock prices over a three-week forward-looking horizon.

---

## ⋆‧°𓏲ּ𝄢 Key Findings & Insights

### 1. The Superiority of Simplicity (Linear Regression Wins)
Despite the complex nature of the stock market, the simplest model outperformed the others. 
* **PSE Dataset R-squared:** LR achieved **0.9609** (vs. SVM's 0.9575 and LSTM's 0.9267).
* **PSEi Dataset R-squared:** LR achieved an outstanding **0.9997** (vs. SVM's 0.9997 and LSTM's 0.9991).

**Insight:** For this specific continuous numerical dataset, traditional statistical methods like Linear Regression provided tighter fits and lower error rates (MSE/MAE/RMSE) than more computationally expensive algorithms.

### 2. Deep Learning vs. Traditional ML
We anticipated the LSTM—a neural network designed for sequence prediction—would excel. However, it struggled more with the variance (MSE of 14.41 on PSE vs. LR's 7.76). 

**Conclusion:** Without additional features like market sentiment analysis or macroeconomic indicators, the simple linear relationships dominated the historical price trends.

### 3. Three-Week Forecasting Viability
Using the trained models, we successfully plotted a three-week forecast for stock prices. 
* **Finding:** Both Linear Regression and SVM successfully mapped out realistic future trends based on the 60-day (and 27-day) timesteps used during training.
* **Conclusion:** These models can serve as highly reliable baseline indicators for short-term trading strategies in the Philippine market.

---

## ⋆‧°𓏲ּ𝄢 The Methodology: A 3-Step Pipeline

Based on our objectives, we developed a systematic pipeline for time-series forecasting:

1. **Data Preprocessing & Scaling:** Historical data was cleaned, and features were normalized using `MinMaxScaler` to ensure larger values didn't skew the model weights.
2. **Time-Step Sequencing:** The data was restructured into sequences (e.g., 60-day windows for LSTM/SVM and 27-day windows for LR) so the models could learn from past consecutive trends.
3. **Training & Evaluation:** Models were trained and subsequently evaluated against test sets using Mean Squared Error (MSE), Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared metrics.

---

## ⋆‧°𓏲ּ𝄢 Project Files & Code

| File | Description | Access |
| :--- | :--- | :--- |
| **Research Paper** | Full documentation: Methodology, Results, and detailed Evaluation Metrics. | [View PDF](https://github.com/alhtb/Stock-Market-Wizard/blob/main/docs/Stock%20Market%20Wizard%20Paper.pdf) |
| **Linear Regression** | Best performing model notebooks for PSE and PSEi. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSE_LR.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSEi_LR.ipynb) |
| **Support Vector Machine** | SVR model implementations for continuous forecasting. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSE_SVM.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSEi_SVM.ipynb) |
| **Deep Learning (LSTM)** | Neural network implementation with Dropout and Regularization. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSE_LSTM.ipynb)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alhtb/stock-market-wizard/blob/main/notebooks/PSEi_LSTM.ipynb) |
| **Datasets** | Raw historical data (2014-2024). | [PSE.csv](data/PSE.csv)<br>[PSEi.csv](data/PSEi.csv) |

## ⋆‧°𓏲ּ𝄢 Tech Stack

* **Pandas & NumPy:** Data manipulation, cleaning, and array structuring.
* **Scikit-Learn:** `LinearRegression`, `SVR`, `MinMaxScaler`, and evaluation metrics.
* **TensorFlow / Keras:** Building the `Sequential` LSTM models with `Dropout` and `Dense` layers.
* **Matplotlib:** Visualizing the actual vs. predicted stock prices.

---

## ⋆‧°𓏲ּ𝄢 Conclusion

Machine learning offers a powerful alternative to traditional fundamental analysis in the Philippine Stock Market. By demonstrating that accessible models like Linear Regression can achieve over 96% variance explanation, we can equip local investors with the mathematical foresight needed to make highly informed, profitable decisions.

***Authors:** Group 2 ([Alberto](https://github.com/paulo10011), [Bruce](https://github.com/SetNickname), Estocado, [Mosinabre](https://github.com/judiemosinabre), [Tuburan](https://github.com/alhtb))*

***Institution:** National University Philippines, Dasmariñas* <br>
***Course:** Introduction to Machine Learning*
