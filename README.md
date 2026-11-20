# NeuroGlia3D

Custom **arivis Vision4D workflow** for 3D soma segmentation, used in the study by **Tütüncü et al.** (*....*).

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

NeuN+ objects corresponding to PV+ somata or located outside the stratum pyramidale were manually excluded. Remaining NeuN+PV− somata were classified as **putative pyramidal cells**.

## 3D radial analysis

After segmentation, soma center coordinates (x, y, z) were extracted and used to calculate 3D radial intensity profiles with a custom Fiji (ImageJ) macro:

**[RadialProfile3D](https://github.com/ngimber/RadialProfile3D)**
