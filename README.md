# assignment_two

**Name**: Sreelekshmi Harikumar  
**University Number**: TCR24CS068  

## 📌 Project Objective
[cite_start]The goal of this project is to explore how time-frequency signal processing and deep learning can be combined to predict stock prices[cite: 145]. [cite_start]By treating multivariate financial data as a signal $X(t)$, we transform it into a 2D spectrogram representation using Short-Time Fourier Transform (STFT) to train a CNN-based regression model[cite: 153, 155].

&nbsp;

## 🛠️ System Pipeline
The workflow follows a structured signal processing and machine learning pipeline:
1. [cite_start]**Data Preparation**: Collection, alignment, and normalization of financial variables[cite: 249].
2. [cite_start]**Signal Processing**: Applying STFT to generate time-frequency spectrograms $S(t, f)$[cite: 253, 255].
3. [cite_start]**Model Development**: Designing and training a Convolutional Neural Network (CNN)[cite: 258].
4. [cite_start]**Analysis**: Evaluating predictions against actual values using Mean Squared Error (MSE)[cite: 262, 264].

&nbsp;

## 📊 Methodology

### 1. Data Preparation
For this assignment, data was collected for three major NSE-listed companies:
* **TCS** (Tata Consultancy Services)
* **INFY** (Infosys)
* **RELIANCE** (Reliance Industries)

[cite_start]Variables included in the multivariate signal $X(t)$ consist of stock prices, revenue, profit, the BSE Sensex index, and the USD-INR exchange rate[cite: 154]. All data was aligned to a common monthly frequency (2020–2024) and normalized using Min-Max scaling.

### 2. Time-Frequency Transformation (STFT)
[cite_start]Since financial time series are non-stationary, STFT is used to analyze frequency content over sliding windows[cite: 162, 165].
* **Window Function**: Hann Window.
* **Window Length**: 12 months.
* **Hop Size**: 1 month (providing maximal overlap for smooth spectrograms).

### 3. CNN Architecture
[cite_start]The model $f_{\theta}$ takes the 2D spectrogram as input to predict the future price $\hat{p}(t+\Delta t)$[cite: 232].
* **Input**: 5-channel spectrogram (Price, Revenue, Profit, Sensex, USD-INR).
* **Layers**: Three Convolutional blocks (Conv2D, Batch Normalization, ReLU, MaxPool) followed by Fully Connected (FC) layers for regression.
* [cite_start]**Loss Function**: Mean Squared Error (MSE)[cite: 264].

&nbsp;
