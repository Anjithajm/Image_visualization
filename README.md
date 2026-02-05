This is a python code to access the hdf5 file of galaxy/quasar/stars cutouts. 
---

## Requirements
-`Python 3.7 or later `
- `astropy`
- `numpy`
- `matplotlib`
- `tensorflow`


Use the following command to install these libraries. 
```
pip install astropy numpy matplotlib tensorflow
```
See, 
```
cutout_data.ipynb file
```

Astronomical images are taken in four optical bands, namely u,g,r and i.
The cutouts of these images are made from the Kilo-degree Survey (KiDS)-DR4 telescope tiles which is publicly available. See https://kids.strw.leidenuniv.nl/DR4/index.php

The cutouts have size (36,36,4).
This means, 36 pixels in x and y-direction of image with number of channels=4. 
1 pixel=0.2 arcsec in KiDS-DR4.

All cutouts are made by using the following code and is publicly available now, https://github.com/Anjithajm/cutout

***How to feed Images into CNN layers***

+----------------------+
|     HDF5 File        |
|   (image dataset)    |
+----------+-----------+
           |
           v
+----------------------+
| Load image column    |
+----------+-----------+
           |
           v
+----------------------+
| Convert to NumPy     |
| array                |
+----------+-----------+
           |
           v
+----------------------+
| Reshape              |
| (N, 36, 36, 4)       |
+----------+-----------+
           |
           v
+----------------------+
| CNN Input Layer      |
| (36, 36, 4)          |
+----------+-----------+
           |
           v
+----------------------+
| Conv2D (7×7)         |
| 64 filters, ReLU     |
+----------+-----------+
           |
           v
+----------------------+
| AveragePooling2D     |
| (3×3)                |
+----------+-----------+
           |
           v
+----------------------+
| Conv2D (1×1)         |
| 64 filters, ReLU     |
+----------------------+

