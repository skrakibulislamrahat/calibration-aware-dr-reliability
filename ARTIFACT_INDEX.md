# Experiment Artifact Index

This file documents the intended role of the major repository directories.

## `configs/`

Experiment-definition and environment metadata. This directory includes global configuration, random seeds, dataset summaries, calibration/tuning plans and results, and package/environment snapshots.

Use these files first when auditing how an experiment was configured.

## `splits/`

Saved data partitions used by the experiments. These files are important for checking leakage controls, repeated-run consistency, and whether different models were evaluated on comparable samples.

## `predictions/`

Selected model-level prediction/probability outputs. These enable recalculation of discrimination, calibration, and error-analysis metrics without retraining the models.

## `metrics_fixed/`

Finalized metric outputs used for reporting. When there is ambiguity between intermediate and finalized values, this directory is the reporting reference.

## `sdi/`

Stability and diagnostic-analysis artifacts used to assess run-to-run behavior and robustness.

## `tables/` and `figures/`

Derived presentation artifacts. These should be traceable to the finalized metrics/predictions rather than treated as primary experimental data.

## `JBHI_1.pdf`

A manuscript snapshot associated with this repository state. It is included for traceability between reported claims and the saved experimental artifacts.

## Boundary of this repository

This is an audit bundle, not a complete training framework. Large checkpoints and a self-contained training pipeline are outside the repository. Do not claim one-command reproducibility from this repository alone.
