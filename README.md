# Pipeline

Create a full machine learning pipeline that produces a random forest model.

This project uses:
- Weights & Biases
- MLflow
- Hydra

## Running the Project

This project can be run using the following command to use your local environment:

```
mlflow run . --no-conda
```

Note that main.py also includes `use_conda=False` in the calls to `mlflow.run()` to use the local environment.  Remove the `--no-conda` flag from the command line and the `use_conda` option to use the environment defined in conda.yml.  (Note that this requires installing Anaconda or Miniconda.)

Additional parameters can be provided on the command line to override those in the config.yaml file, as shown below:

```
mlflow run . --no-conda -P hydra_options="random_forest_pipeline.random_forest.n_estimators=10" -P hydra_options="data.test_size=0.25"
```

To create the production run, change the project_name to "genre_classification_prod" by running:
```
mlflow run . --no-conda -P hydra_options="main.project_name=genre_classification_prod"
```
