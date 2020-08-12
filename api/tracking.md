---
title: Tracking in CRAL
description: Integrate experiment tracking to your deep learning project.
published: true
date: 2020-08-12T10:20:22.325Z
tags: 
editor: markdown
---

# cral.tracking
The `cral.tracking` module provides a high-level API for tracking and logging metadata and artifacts for deep learning algorithms.

CRAL internally uses [MLFlow](https://mlflow.org/) to log your experiments.

## set_experiment
```py
set_experiment(id)
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| id | string | . | Experiment ID generated on *track.segmind.com*  |

## log_params
Log a set of parameters for the current run. 
[](log_param)
```py
parameter_dict = {'key1':10, 'key2':20}
log_params(parameter_dict)
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| params | dict | | Dictionary of parameters. param_name -> value  |

## log_metrics
Log multiple metrics for the current run. 
```py
metric_dict = {'metric1':1, 'metric2':1e-2}
log_metrics(metrics=metric_dict, step=1)
```

**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| metrics | dict | | Dictionary of metrics. metric_name -> value |
| step | Int | 0 | Step at which to log the specified metrics. |

## log_artifact
Log all the contents of a local directory as artifacts of the run. 
```py
log_artifact(key, path)
```

**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| key | str | | name of the artifact |
| path | str | | path to the artifact file |

## KerasCallback
Callback for auto-logging metrics and parameters. Records available logs after each epoch. Records model structural information as params when training begins
```py
from cral.tracking import KerasCallback

cral_cb = KerasCallback(log_evry_n_step=None)

#Define your keras model
model = keras.Model(....)
model.fit(other_keras_arguments,callbacks=[cral_cb])
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| log_evry_n_step | None, Int | None | If Integer(N), then metrics is logged after every **N** batch, else if (None) logged at the end of every epoch  |

