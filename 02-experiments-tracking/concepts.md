## important concepts

- ML experiment: the process of building an ML model
- Experiment run: each trial in an ML experiment
- Run artifact: any file that is associated with an ML run
- Experiment metadata

## Experiment tracking

Experiment tracking is the process of keeping track of all the relevant information from an ML experiment, which includes:

- souce code
- environment
- data
- model
- hyperparameters
- metrics

## why it is important

- Reproducibility
- Organization
- Optimization

## MLFlow

Definition: An open source platform for the machine learning lifecycle

it's just a python package that can be installed with pip, and it contains four main modules:

- Tracking
- Models
- Model Registry
- Projects

## Tracking experiments with MLFlow

The MLflow tracking module allows you to organize your experiments into runs, and to keep track of.

- Parameters
- Metrics
- Metadata
- Artifacts
- Models

Along with this information, MLflow automatically logs extra information about the run:

- Source code
- version of the code
- start and end time
- Author

### start mlflow 
```
mlflow ui --backend-store-uri sqlite:///mlflow.db
```