---
title: Tracking in CRAL
description: Integrate experiment tracking to your deep learning project.
published: true
date: 2020-06-15T09:18:09.903Z
tags: 
editor: markdown
---

# cral.tracking
The `cral.tracking` module provides a high-level API for tracking and logging metadata and artifacts for deep learning algorithms.

CRAL internally uses [MLFlow](https://mlflow.org/) to log your experiments.

## set_experiment
```py
set_experiment()
```

## log_params
Log a batch of params for the current run. If no run is active, this method will create a new active run.

```py
log_params(*args, **kwargs)
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| params | dict | | Dictionary of parameters.  |


## log_metrics

## log_artifacts

## KerasCallback