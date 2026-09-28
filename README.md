# cumlative_usage

> [!IMPORTANT]
> **Archived / no longer actively maintained.**
>
> This repository is preserved as a small historical example of fitting an exponential model to cumulative cloud-storage usage. No further feature development or compatibility maintenance is planned.

## Historical purpose

The script `cumlative_usage.py` demonstrates:

- cumulative usage from a short daily-usage series,
- nonlinear curve fitting with `scipy.optimize.curve_fit`,
- NumPy array operations, and
- plotting the observed and fitted cumulative usage with Matplotlib.

The original example uses seven days of sample data totaling 28 GB and fits:

```math
F(t) = A \cdot e^{kt} - A
```

This is an educational example, not a cloud billing or forecasting system.

## Final dependency snapshot

For reproducibility, the final archived environment is recorded in `requirements.txt`:

- Python **3.12+**
- `numpy==2.5.3`
- `scipy==1.18.1`
- `matplotlib==3.11.2`

Install with:

```console
python -m pip install -r requirements.txt
```

Run the historical example with:

```console
python cumlative_usage.py
```

## Scope and limitations

The fitted curve is derived from a very small synthetic sample and should not be treated as a production forecast. Real cloud usage and billing depend on service-specific pricing, tiering, dimensions, retention, and workload behavior.

The original result image is retained in `sample_result_graph.png`.

## Repository status

No further dependency automation, bot-driven maintenance, scheduled CI, or feature work is planned. The repository is intended to remain public and read-only after GitHub archival.
