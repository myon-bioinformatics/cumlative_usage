# cumlative_usage
This repository contains a Python script that models the cumulative cloud storage usage using an exponential function. The script fits an exponential model to daily usage data and plots the cumulative usage over a period of days.[default= 7 days]

## Requirements

- Python 3.x
- NumPy
- SciPy
- Matplotlib

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/cumulative-cloud-storage-usage.git
    ```
2. Navigate to the project directory:
    ```bash
    cd cumulative-cloud-storage-usage
    ```
3. Install the required packages:
    ```bash
    pip install numpy scipy matplotlib
    ```

## Usage

Run the script to see the cumulative usage plot:

```bash
python cumulative_usage_model.py
```

## Script Overview
The script performs the following steps:

Data Preparation:
- Define the number of days and daily usage.
- Calculate the cumulative usage.

Model Definition:
- Define the exponential model for cumulative usage.

Model Fitting:
- Fit the model to the data to determine the parameters 𝐴 and 𝑘.

Plotting:
- Plot the actual cumulative usage and the model's cumulative usage.
