# Experiment tracking setup



````
## Overview
To maintain research reproducibility, all optimization runs, hyperparameter modifications, and hardware telemetry values are captured simultaneously using MLflow and Weights & Biases (W&B).

## Infrastructure Setup
* **MLflow Backend**: Hosted locally via a tracking URI layer to save optimization logs and artifact files (circuit diagrams, optimization landscapes).
* **Weights & Biases Cloud**: Serves as our centralized repository for live metrics tracking, interactive runs comparison, and team dashboards.

## Operational Command
```bash
# Launching the internal verification portal
mlflow ui --port 5000
```
````
