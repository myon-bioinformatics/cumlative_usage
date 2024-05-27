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

# Guidance 
## 1. Mission
### Introduction
In a world overflowing with pay-as-you-go services, such as AWS, Azure, and OCI, you can probably check cumulative metrics... But wouldn’t you like to know the formulas and graphs representing cumulative usage?

(No, it's just that I thought it would make a good Qiita article, not that I always think this way... haha)

### Challenge
Assume cumulative usage of 28 GB over 7 days.
Set daily usage as [3, 3, 5, 2, 8, 4, 2].
The goal is to find a function that returns the following values (in GB) for the given number of days.
🐎🐎🐎

```math
F(1) = 3
```

```math
F(7) = 28
```

## 2. Mathematics
This is nonlinear. Once you realize it’s not a linear graph, using an exponential function usually works well.

Let the machine handle fitting in the nonlinear function model!🚀🚀🚀

Search for the specific values of the parameter constants (A, k) through fitting.

```math
Assumption: A, k \in \mathbb{R}
```

𝐹(𝑡): The integral of daily usage 𝑓(𝑡) representing cumulative usage (GB)
```math
F(t) = A \cdot e^{kt} - A
```
𝑓(𝑡): The derivative of cumulative usage 
```math
f(t) = A \cdot k \cdot e^{kt}
```

## 3. Implementation
```python
import numpy as np
from scipy.optimize import curve_fit
import matplotlib.pyplot as plt

# Number of days
days = np.array([1, 2, 3, 4, 5, 6, 7])
# Daily usage
daily_usage = np.array([3, 3, 5, 2, 8, 4, 2])
# Cumulative usage
cumulative_usage = np.cumsum(daily_usage)

# Cumulative usage model
def cumulative_model(t, A, k):
    return A * np.exp(k * t) - A

# Fitting
params, covariance = curve_fit(cumulative_model, days, cumulative_usage, p0=[1, 0.1])
A, k = params
print(f"A: {A}, k: {k}")

# Plotting the graph
plt.figure(figsize=(10, 6))
plt.plot(days, cumulative_usage, 'o', label='Cumulative Usage (Observed)')
plt.plot(days, cumulative_model(days, A, k), '-', label='Cumulative Usage (Model)')
plt.xlabel('Days')
plt.ylabel('Cumulative Usage (GB)')
plt.legend()
plt.title(f'Cumulative Usage Model: A={A:.2f}, k={k:.2f}')
plt.grid(True)
plt.show()
```
## 4. Results
### Exponential Function Parameters (A, k)

𝐴=56.14
𝑘=0.0584
👩‍💻👩‍💻👩‍💻

```math
Cumulative Usage (GB): F(t) = 56.14 \cdot e^{0.0584t} - 56.14
```
```math
Daily Usage (GB): f(t) = 56.14 \cdot 0.0584 \cdot e^{0.0584t}
```

### Here's what the graph looks like
It may look linear due to the small data sample, but it is a nonlinear function.
🧑‍💻🧑‍💻🧑‍💻





