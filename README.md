# Enhancing Electricity Price Forecasting Accuracy with Detection-Informed Hybrid Model

## Overview
Welcome to the GitHub repository for our project on improving electricity price forecasting using a detection-informed hybrid model. This project combines Gated Recurrent Units (GRU) and eXtreme Gradient Boosting (XGBoost) to create a robust model capable of handling complex, time-varying data patterns and concept drift, which are common challenges in the energy sector.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Data Collection](#data-collection)
6. [Model Training](#model-training)
7. [Results](#results)
8. [Concept Drift Detection](#concept-drift-detection)
9. [Retraining Strategy](#retraining-strategy)
10. [Ethical Considerations](#ethical-considerations)
11. [Future Enhancements](#future-enhancements)
12. [Contributing](#contributing)
13. [License](#license)

## Introduction

This project addresses the critical challenge of forecasting electricity prices amidst the growing integration of renewable energy sources, which introduces variability and unpredictability. Traditional forecasting methods often fall short due to these complexities. Our approach involves a novel hybrid model that enhances forecasting accuracy and adapts to changes in data patterns, known as concept drift.

## Project Structure

- `data/`: Directory containing the datasets used in the project.
- `notebooks/`: Jupyter notebooks for data preprocessing, model training, and analysis.
- `scripts/`: Python scripts for running the model and performing tasks.
- `models/`: Directory for saving trained models.
- `results/`: Directory for storing results and visualizations.
- `README.md`: Project documentation.
- `LICENSE`: License for the project.

## Installation

### Prerequisites

- Python 3.7 or higher
- Virtual environment (optional but recommended)

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

### Running the Model

1. **Preprocess the data:**

    ```bash
    python scripts/preprocess_data.py
    ```

2. **Train the model:**

    ```bash
    python scripts/train_model.py
    ```

3. **Evaluate the model:**

    ```bash
    python scripts/evaluate_model.py
    ```

### Notebook Exploration

- Explore the Jupyter notebooks in the `notebooks/` directory to see step-by-step data analysis and model training processes.

## Data Collection

The data used in this project includes hourly electricity prices from Spanish cities (2015-2019), weather data, and other energy-related metrics. The data is collected from multiple sources to ensure diversity and comprehensiveness.

- **Electricity Prices:** [Open Power System Data](https://data.open-power-system-data.org/time_series/)
- **Weather Data:** [OpenWeatherMap](https://openweathermap.org/)
- **Energy Data:** [ENTSOE](https://www.entsoe.eu/)

## Model Training

### Hybrid Model

- **GRU (Gated Recurrent Unit):** Used for handling time-series data and capturing temporal patterns.
- **XGBoost:** Integrated to correct residual errors from the GRU model, enhancing overall accuracy.

### Training Process

1. Preprocess the data by normalizing and feature engineering.
2. Train the GRU model to capture time-series patterns.
3. Use XGBoost to correct errors from the GRU model.
4. Combine the outputs to form the final hybrid model.

## Results

### Accuracy Improvement

- **MAE (Mean Absolute Error):** Reduced from 0.017 to 0.014.
- **RMSE (Root Mean Squared Error):** Improved from 0.025 to 0.020.
- **R² Value:** Increased from 0.85 to 0.89.

The results demonstrate significant improvements in forecasting accuracy, showcasing the hybrid model's effectiveness.

## Concept Drift Detection

Concept drift, or changes in data patterns over time, is detected using:

- **Kolmogorov-Smirnov (KS) Test:** Identifies changes in distribution.
- **Wasserstein Distance:** Measures the magnitude of distributional changes.

These methods ensure the model remains accurate and relevant as data evolves.

## Retraining Strategy

The model uses a windowing technique for retraining to maintain high performance:

- **Window Size:** Data is retrained using a small window of recent data to quickly adapt to changes.
- **Efficiency:** Ensures the model stays responsive without high computational costs.

## Ethical Considerations

- **Data Anonymization:** Personal data is anonymized to protect privacy.
- **Data Protection Compliance:** Adheres to GDPR and other regulations.
- **Ethical AI Practices:** Ensures responsible use of data and algorithms.

## Future Enhancements

- **Integration of Economic Indicators:** Adding more features to improve accuracy.
- **Advanced Concept Drift Techniques:** Exploring more sophisticated methods for detecting changes in data patterns.
- **Real-Time Forecasting System:** Developing a system for immediate application in grid management.

## Contributing

Contributions are welcome! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) for more details on how to get involved.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.