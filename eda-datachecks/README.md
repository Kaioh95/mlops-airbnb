# Instructions
This component uses MLFlow and W&B so, in order to successfully run it, you are going to need to run the previous section, "eda-datasegregation", to store the artifacts on W&B.

This code uses deterministic and non-deterministic testing to make checks on our data, in order to prevent bad data to go into our pipeline.

Even though this step is interactive, and not based on scripts, we are still going to use MLflow
to ensure a reproducible analysis, by fixing the environment in the ``conda.yml`` file.

## Run steps

```bash
mlflow run .
```

## In case of errors

When you make an error writing your ``conda.yml`` file, you might end up with an environment for the pipeline or one of the components that is corrupted. Most of the time ``mlflow`` realizes that and creates a new one every time you try to fix the problem. However, sometimes this does not happen, especially if the problem was in the ``pip`` dependencies. In that case, you might want to clean up all conda environments created by ``mlflow`` and try again. In order to do so, you can get a list of the environments you are about to remove by executing:

```bash
conda info --envs | grep mlflow | cut -f1 -d" "
```

If you are ok with that list, execute this command to clean them up:

**NOTE**: this will remove ALL the environments with a name starting with mlflow. Use at your own risk

```bash
for e in $(conda info --envs | grep mlflow | cut -f1 -d" "); do conda uninstall --name $e --all -y;done
```

This will iterate over all the environments created by mlflow and remove them.
