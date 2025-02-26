# ThinkClock Battery Analysis System

A comprehensive Python framework for battery data analysis, designed for researchers and engineers working with lithium-ion battery datasets. This project provides tools for analyzing battery aging through electrochemical impedance spectroscopy (EIS) and incremental capacity analysis (ICA).

## Features

- **3D Electrochemical Impedance Spectroscopy (EIS) Visualization**: Track impedance changes with battery aging through interactive 3D Nyquist plots.
- **Incremental Capacity Analysis (dQ/dV)**: Monitor capacity fade and cell degradation through peak evolution analysis.
- **Machine Learning Integration**: Predict battery capacity from impedance features using Random Forest algorithms.
- **Automatic Data Processing**: Automatically identifies and processes data files with minimal user configuration.
- **Synthetic Data Generation**: Creates realistic battery data for testing when real data is unavailable.

## Requirements

- Python 3.6+
- NumPy
- Pandas
- Matplotlib
- SciPy
- Scikit-learn

## Installation

Clone the repository and install the required packages:

```bash
git clone https://github.com/Ashish032002/Thinklabs.git
cd thinklock-battery-analysis
pip install -r requirements.txt
```

## Usage

1. Place your battery dataset in the `archive/cleaned_dataset` directory or update the `data_path` variable in the script.
2. Run the main script:

```bash
python Thinklabs.py
```

The script will automatically:
1. Search for EIS and cycle data files
2. Create 3D visualizations of impedance changes with aging
3. Perform incremental capacity analysis
4. Train a machine learning model to predict capacity from impedance features

## Input Data Structure

The script is flexible and can work with various data formats:

- **EIS Data**: Files containing real and imaginary impedance data (Re(Z) and Im(Z))
- **Cycle Data**: Files containing voltage and capacity/current measurements
- **Metadata**: Optional CSV file with additional information about the files

## Output Files

The script generates several visualization files:

- `3d_eis_plot.png`: 3D visualization of impedance spectra evolution
- `3d_dqdv_plot.png`: 3D visualization of dQ/dV peak evolution
- `nyquist_*.png`: Individual Nyquist plots for each cycle
- `voltage_capacity_*.png`: Individual voltage-capacity curves
- `dqdv_*.png`: Individual dQ/dV plots for each cycle
- `capacity_prediction.png`: Model performance on capacity prediction
- `feature_importance.png`: Feature importance from the ML model

## Dataset

This system was designed to work with NASA's battery dataset, but it can be adapted to work with other battery datasets with similar data structures.

If you don't have a dataset, the script will generate synthetic data for demonstration purposes.

## Technical Details

### Task A: 3D EIS Analysis

- Extracts impedance data from various file formats
- Creates Nyquist plots for each measurement
- Generates a 3D visualization showing impedance changes with aging

### Task B: Incremental Capacity Analysis

- Processes voltage and capacity/current data
- Calculates differential capacity (dQ/dV) curves
- Creates a 3D visualization showing peak evolution with aging

### Task C: ML Model for Capacity Prediction

- Extracts features from EIS measurements
- Trains a Random Forest model to predict capacity
- Evaluates model performance and visualizes feature importance



## Acknowledgments

- NASA for providing battery datasets for research
