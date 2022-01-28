# MLflow Logging API Quickstart
This notebook illustrates how to use the MLflow logging API to start an MLflow run and log the model, model parameters, evaluation metrics, and other run artifacts to the run. The easiest way to get started using MLflow tracking with Python is to use the MLflow autolog() API. If you need more control over the metrics logged for each training run, or want to log additional artifacts such as tables or plots, you can use the mlflow.log_metric() and mlflow.log_artifact() APIs demonstrated in this notebook.

# Setup
If you are using a cluster running Databricks Runtime, you must install the mlflow library from PyPI. See Cmd 3.
If you are using a cluster running Databricks Runtime ML, the mlflow library is already installed.
This notebook creates a Random Forest model on a simple dataset and uses the MLflow Tracking API to log the model and selected model parameters and metrics.

# Notebook Reference Link
https://databricks.com/notebooks/gallery/MLflowLoggingAPIPythonQuickstart.html
