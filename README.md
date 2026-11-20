# NeuroGlia3D

Custom **arivis Vision4D workflow** for 3D segmentation of PV+ interneurons and NeuN+ somata, used in the radial analysis of microglia–PVI interactions.

## Segmentation

**PV+ somata**
- Morphological opening: 1.5 µm
- Gaussian smoothing: σ = 20 µm
- Otsu thresholding
- Minimum volume: >400 µm³

**NeuN+ somata (Blob Finder)**
- Diameter: 6 µm
- Threshold: 8.36
- Watershed: 29.5%
- Minimum volume: >100 µm³

## Manual curation

NeuN+ objects overlapping PV+ somata or located outside the stratum pyramidale were manually excluded. Remaining NeuN+PV− somata were classified as **putative pyramidal cells**.
