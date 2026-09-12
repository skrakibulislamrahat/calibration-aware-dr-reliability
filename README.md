# Calibration-Aware and Seed-Stable Deep Learning for Diabetic Retinopathy

> **Research hub:** [Portfolio view](https://skrakibulislamrahat.github.io/#project-calibration) · [Artifact index](ARTIFACT_INDEX.md) · [Finalized metrics](metrics_fixed/) · [Citation metadata](CITATION.cff)

This repository is the **experiment audit and reproducibility-artifact bundle** for a diabetic-retinopathy study focused on probability calibration, robustness across random seeds, and generalization across retinal-imaging datasets.

The emphasis is not only discrimination performance, but whether predicted probabilities remain reliable and whether conclusions are stable across repeated runs.

## Research focus

The experimental artifacts support analysis of:

- predictive discrimination on retinal fundus images;
- probability calibration before and after recalibration;
- variability across random seeds;
- dataset-shift/generalization behavior;
- predefined data splits and experiment configurations;
- traceability from reported tables/figures back to saved metrics and predictions.

## Datasets

The study uses public retinal-imaging benchmarks including:

- **APTOS 2019** for primary experiments;
- **Messidor-2** for external/generalization analysis.

Raw datasets are not redistributed in this repository.

## Repository structure

```text
.
├── configs/          # global configuration, seeds, environment snapshots, tuning plans/results
├── figures/          # manuscript/result figures
├── metrics_fixed/    # finalized evaluation metrics used for reporting
├── predictions/      # selected probability/prediction outputs
├── sdi/              # stability and diagnostic-analysis artifacts
├── splits/           # saved dataset split definitions
├── tables/           # derived manuscript/reporting tables
├── JBHI_1.pdf        # manuscript snapshot associated with this artifact bundle
├── ARTIFACT_INDEX.md # how to audit the experiment outputs
├── .gitignore
└── README.md
```

## Reproducibility scope

This repository is intentionally an **artifact bundle rather than a plug-and-play training package**. It preserves experiment inputs/metadata and finalized outputs needed to audit the reported analysis: configuration files, random seeds, split definitions, environment snapshots, prediction outputs, tuning records, metrics, tables, and figures.

Training code and large model checkpoints are not represented here as a complete standalone training framework. Accordingly, the repository should be used for **result traceability and experiment auditing**, not described as a one-command reproduction package.

## Audit workflow

A reviewer or collaborator can use the repository in this order:

1. inspect `configs/global_config.json`, `configs/seeds.json`, and the environment snapshots;
2. inspect `splits/` to verify predefined sample partitions;
3. inspect `predictions/` and `metrics_fixed/` for saved model outputs and finalized metrics;
4. trace statistical/diagnostic analyses through `sdi/`;
5. compare `tables/` and `figures/` with the manuscript snapshot.

See [`ARTIFACT_INDEX.md`](ARTIFACT_INDEX.md) for more detail.

## Reporting policy

Only finalized results in `metrics_fixed/` should be treated as reporting artifacts. Intermediate files should not be substituted for the finalized analysis without documenting the change.

## Research status

This repository preserves a manuscript-associated research snapshot. Formal citation metadata should be updated when a stable publication record/DOI is available.

## Responsible use

The repository is for research transparency and reproducibility auditing. It is not a clinical diagnostic system and should not be used for patient-care decisions.
