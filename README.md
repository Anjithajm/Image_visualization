# Galaxy / Quasar / Star Cutouts (HDF5)

This repository contains Python code to read HDF5 files of astronomical image cutouts
(galaxies, quasars, and stars) and to prepare these images as input for
Convolutional Neural Networks (CNNs) and their visualization.

The accompanying Jupyter notebook demonstrates how to load the data and use it
for deep learning applications.

---

## Requirements

- Python 3.7 or later
- astropy
- numpy
- matplotlib
- tensorflow

Install the required packages using:

```bash
pip install astropy numpy matplotlib tensorflow
```
## Data description

-Images are provided in four optical bands: u, g, r, i
-Cutouts are extracted from the Kilo-Degree Survey (KiDS-DR4) telescope tiles: https://kids.strw.leidenuniv.nl/DR4/index.php

## Cutout Properties
- shape = (36,36,4)
- Spatial size: 36 × 36 pixels
- Channels: 4 (u, g, r, i)
- Pixel scale: 0.2 arcsec per pixel (for KiDS-DR4)

## Cutout generation
All cutouts are generated using the publicly available code: https://github.com/Anjithajm/cutout

## Jupyter Notebook
```bash
cutout_data.ipynb
```
Demonstrates how to load the HDF5 file, reshape the image data, and feed it into CNN layers.

## Example CNN Input Flow
-  HDF5 file
  → load image dataset
  → NumPy array
  → reshape to (N, 36, 36, 4)
  → CNN input layer
  → Conv2D + pooling layers

## Additional info
For the multi-class classification task (GALAXY, QSO, STAR), the three separate datasets must first be combined into a single dataset. After stacking the stars, qso, and galaxies HDF5 files, the image data are loaded from the image column.

The target labels are provided by the SPECTYPE column, which indicates the object class (STAR, GALAXY, or QSO). The SPECTYPE values are stored as strings, not as numeric labels (e.g., 0 or 1), and therefore must be encoded before training the CNN.

## Important note
- Preprocess the image data before feeding it into a deep neural network.
- Be careful with the preprocessing since flux information is really important for astronomical data.
  
