---
title: Tracking in CRAL
description: Integrate experiment tracking to your deep learning project.
published: true
date: 2020-06-18T07:16:51.955Z
tags: 
editor: undefined
---

# cral.tracking
The `cral.tracking` module provides a high-level API for tracking and logging metadata and artifacts for deep learning algorithms.

CRAL internally uses [MLFlow](https://mlflow.org/) to log your experiments.

## set_experiment
```py
set_experiment(*args, **kwargs)
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| id | string | . | Experiment ID generated on *track.segmind.com*  |

## log_params
Log a set of parameters for the current run. 
[](log_param)
```py
log_params(*args, **kwargs)
```
**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| params | dict | | Dictionary of parameters. param_name -> value  |

## log_metrics
Log multiple metrics for the current run. 
```py
log_metrics(*args, **kwargs)
```

**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| metrics | dict | | Dictionary of metrics. metric_name -> value |
| step | Int | 0 | Step at which to log the specified metrics. |

## log_artifacts
Log all the contents of a local directory as artifacts of the run. 
```py
log_artifacts(*args, **kwargs)
```

**Arguments**
| Name | Type | Default | Description |
|---|---|---|---|
| metrics | dict | | Dictionary of metrics. metric_name -> value |
| step | Int | 0 | Step at which to log the specified metrics. |

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

