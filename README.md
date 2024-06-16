# Enhancing Electricity Price Forecasting Accuracy with Detection-Informed Hybrid Model

## Overview

Welcome to the GitHub repository for our project on improving electricity price forecasting using a detection-informed hybrid model. This project combines Gated Recurrent Units (GRU) and eXtreme Gradient Boosting (XGBoost) to create a robust model capable of handling complex, time-varying data patterns and concept drift, which are common challenges in the energy sector. Upon detecting concept drift, the model is designed to retrain itself to adapt to the new data patterns and maintain forecasting accuracy.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Data Collection](#data-collection)
6. [Model Training and Evaluation](#model-training-and-evaluation)
7. [Results](#results)
8. [Concept Drift Detection and Retraining](#concept-drift-detection-and-retraining)
9. [Ethical Considerations](#ethical-considerations)
10. [Future Enhancements](#future-enhancements)
11. [Contributing](#contributing)
12. [License](#license)

## Introduction

This project addresses the critical challenge of forecasting electricity prices amidst the growing integration of renewable energy sources, which introduces variability and unpredictability. Traditional forecasting methods often fall short due to these complexities. Our approach involves a novel hybrid model that enhances forecasting accuracy and adapts to changes in data patterns, known as concept drift. When concept drift is detected, the model undergoes retraining to adapt to the new data patterns, ensuring continuous high accuracy.

## Project Structure

- `data/`: Directory containing the datasets used in the project.
- `notebooks/`: Jupyter notebooks, including `conceptDriftResults4.ipynb` for running the model and obtaining results.
- `README.md`: Project documentation.
- `LICENSE`: License for the project.

## Installation

### Prerequisites

- Python 3.7 or higher
- Jupyter Notebook

### Steps

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/electricity-price-forecasting.git
    cd electricity-price-forecasting
    ```

2. **Create and activate a virtual environment:**

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install the required packages:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Set up the data:**

    - Download the dataset and place it in the `data/` directory. The dataset can be obtained from [Open Power System Data](https://data.open-power-system-data.org/time_series/) and other specified sources.

## Usage

### Running the Model using Jupyter Notebook

1. **Start Jupyter Notebook:**

    ```bash
    jupyter notebook
    ```

2. **Open the Notebook:**

    - Navigate to the `notebooks/` directory and open `conceptDriftResults4.ipynb`.

3. **Run the Notebook:**

    - Execute the cells in `conceptDriftResults4.ipynb` sequentially. The notebook includes data preprocessing, model training, evaluation, and results visualization. It also demonstrates the process of detecting concept drift and retraining the model to adapt to new data patterns.

    - Make sure the dataset is in the appropriate format and placed in the `data/` directory as specified in the notebook.

### Notebook Features

- **Data Preprocessing:** Cleans and normalizes data for training.
- **Model Training:** Trains the hybrid GRU-XGBoost model.
- **Evaluation:** Evaluates model performance and visualizes results.
- **Concept Drift Detection and Retraining:** Includes steps for detecting and handling concept drift, followed by retraining the model to adapt to new data patterns.

## Data Collection

The data used in this project includes hourly electricity prices from Spanish cities (2015-2019), weather data, and other energy-related metrics. The data is collected from multiple sources to ensure diversity and comprehensiveness.

- **Electricity Prices:** [Open Power System Data](https://data.open-power-system-data.org/time_series/)
- **Weather Data:** [OpenWeatherMap](https://openweathermap.org/)
- **Energy Data:** [ENTSOE](https://www.entsoe.eu/)

## Model Training and Evaluation

### Hybrid Model

- **GRU (Gated Recurrent Unit):** Used for handling time-series data and capturing temporal patterns.
- **XGBoost:** Integrated to correct residual errors from the GRU model, enhancing overall accuracy.

### Training Process

1. Preprocess the data by normalizing and feature engineering.
2. Train the GRU model to learn patterns in the time-series data.
3. Use XGBoost to correct any errors made by the GRU model.
4. Combine the outputs to form the final hybrid model.
5. Implement a retraining strategy to ensure the model adapts to new data patterns when concept drift is detected.

## Results

### Accuracy Improvement

- **MAE (Mean Absolute Error):** Reduced from 0.017 to 0.014.
- **RMSE (Root Mean Squared Error):** Improved from 0.025 to 0.020.
- **R² Value:** Increased from 0.85 to 0.89.

These metrics demonstrate significant improvements in forecasting accuracy, showcasing the hybrid model's effectiveness.

## Concept Drift Detection and Retraining

### Concept Drift Detection

Concept drift refers to the change in the underlying data distribution over time, which can affect model performance. This project uses:

- **Kolmogorov-Smirnov (KS) Test:** To identify changes in distribution.
- **Wasserstein Distance:** To measure the magnitude of distributional changes.

### Retraining on Drift Detection

Upon detecting concept drift, the model undergoes a retraining process to adapt to the new data patterns. This involves:

- **Windowing Technique:** Using a fixed-size window of the most recent data to retrain the model periodically, ensuring the model remains responsive to the latest data trends.
- **Retraining:** Updating the GRU and XGBoost components of the hybrid model with new data to maintain accuracy and relevance.

This process ensures that the model continues to provide accurate forecasts even as the data evolves over time.

## Ethical Considerations

- **Data Anonymization:** Personal data is anonymized to protect privacy.
- **Data Protection Compliance:** Adheres to GDPR and other regulations.
- **Ethical AI Practices:** Ensures responsible use of data and algorithms.

## Future Enhancements

- **Integration of Economic Indicators:** Adding more features to improve accuracy.
- **Advanced Concept Drift Techniques:** Exploring more sophisticated methods for detecting changes in data patterns.
- **Real-Time Forecasting System:** Developing a system for immediate application in grid management.

<!-- ## Contributing

Contributions are welcome! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) for more details on how to get involved.
  -->
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.