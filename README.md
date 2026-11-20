# NeuroGlia3D

**arivis Vision4D workflow for 3D neuronal soma segmentation in studies of microglia–parvalbumin interneuron (PVI) interactions.**

## Overview

This repository provides a custom **arivis Vision4D** workflow used to segment parvalbumin-positive (**PV+**) somata and NeuN-positive (**NeuN+**) somata in 3D microscopy images. After manual curation, NeuN+ / PV− somata within the stratum pyramidale are classified as **putative pyramidal cells**.

The segmentation is part of a broader 3D radial analysis of microglia–PVI interactions. The steps documented below describe neuronal soma segmentation and classification; they do not, by themselves, specify microglial segmentation or radial-distance measurements.

## Requirements

- **arivis Vision4D** (compatible version required; exact version not specified)
- Calibrated 3D microscopy datasets containing **PV** and **NeuN** fluorescence channels
- Manual review of segmented objects and their anatomical location

## Segmentation workflow

### 1. PV+ soma segmentation

Apply the following operations to the PV channel, in order:

1. **Morphological opening:** 1.5 µm
2. **Gaussian smoothing:** σ = 20 µm
3. **Thresholding:** Otsu method
4. **Volume filter:** retain objects **> 400 µm³**

### 2. NeuN+ soma segmentation

Segment the NeuN channel separately using **Blob Finder** with these settings:

| Parameter | Value |
| --- | --- |
| Blob diameter | 6 µm |
| Threshold | 8.36 |
| Watershed | 29.5% |
| Minimum retained volume | > 100 µm³ |

### 3. Manual curation and classification

Manually exclude NeuN+ segmented profiles that:

- Correspond to a **PV+ soma**, or
- Are located **outside the stratum pyramidale**.

Classify the remaining **NeuN+ / PV− somata** as **putative pyramidal cells**.

## Using the workflow

1. Download the arivis workflow file from this repository and load it in a compatible version of Vision4D.
2. Open a calibrated 3D dataset and confirm the **PV** and **NeuN** channel assignments.
3. Run the PV+ and NeuN+ segmentation steps using the parameters above.
4. Inspect the results in 3D, perform the manual exclusions, and use the curated objects for downstream analysis.

> **Note:** The workflow file and its exact import procedure should be documented alongside the uploaded pipeline. Segmentation settings may need validation for other imaging conditions or voxel sizes.

## Limitations

- NeuN+ / PV− classification as *putative* pyramidal cells depends on anatomical location and manual exclusion; it is not independent cell-type validation.
- The workflow is **not fully automated**, because manual curation is required.
- Microglial segmentation and radial-analysis procedures are **not described here** and should be documented separately if included in this repository.

## Citation

If you use this workflow, please reference this repository and cite the associated publication when available.
