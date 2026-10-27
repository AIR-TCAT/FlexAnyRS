# FlexAnyRS

**FlexAnyRS: Parameter-Efficient Set-to-Set Remote Sensing Generation under Imperfect Alignment**

<p align="center">
  <img src="figures/fig03_overview.png" width="100%" alt="FlexAnyRS method overview">
</p>

<p align="center">
  <sub>
  Overview of FlexAnyRS. <b>Top (training):</b> PD-SPVAE encodes any set of source modalities into a shared latent space through a shared encoder backbone and a shared posterior head; LatentAnchor regresses the conditional mean of the target latent conditioned on the target-sensor metadata, and a frozen joint DiT with LatentAlignment synthesizes the target set. <b>Bottom (inference):</b> an arbitrary source set is encoded, anchored and decoded back to an arbitrary target set, so both the input and the output cardinality may vary. High-resolution version: <a href="figures/fig03_overview.pdf">figures/fig03_overview.pdf</a>.
  </sub>
</p>

## Overview

Earth observation increasingly relies on complementary multi-modal imagery, yet acquiring every modality over the same area is rarely possible, which makes cross-modal generation a basic means of completing missing observations and augmenting downstream training data. Existing approaches treat SAR, RGB, NIR and other modalities as closed discrete categories that ignore the underlying sensor parameters, so a single model can hardly cover arbitrary modality combinations and parameter configurations; even with a shared backbone, modalities under new sensor parameters can only be added by retraining encoders or appending branches.

FlexAnyRS instead takes **imaging parameters as the basic representation unit** and performs set-to-set generation with a variable cardinality through subset selection and parameter extrapolation in the parameter space. It consists of:

- **PD-SPVAE** — a shared encoder backbone and a shared posterior head across modalities, projecting all modalities into one latent space.
- **Regression-to-conditional-mean generation** — `LatentAnchor`, `CrossModalCondition` and `LatentAlignment` remove the scale mismatch between modalities and improve the structural consistency between generated and source imagery.
- **Three-stage parameter integration** — conditional anchoring, residual insertion and few-shot calibration, enabling rapid integration of modalities under new sensor parameters.

The framework is developed and evaluated on **PentaRS**, a parameterized cross-modal remote sensing benchmark introduced in the paper.

## Code availability

**The code will be released upon acceptance of the paper.**

This repository currently hosts the paper's method overview figure. Training and evaluation code, configuration files, pretrained weights and the benchmark construction scripts will be made publicly available here once the paper is accepted.

## Citation

BibTeX will be provided once the paper is published.

## Contact

For questions about the paper or this repository, please open an issue.
