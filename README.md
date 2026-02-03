This is a python code to access the hdf5 file of galaxy/quasar/stars cutouts. 
---

## Requirements
-`Python 3.7 or later `
-`astropy`
-`numpy`
-`matplotlib`

Use the following command to install these libraries. 
```
pip install astropy numpy matplotlib
```
Astronomical images are taken in four optical bands, namely u,g,r and i.
The cutouts of these images are made from the Kilo-degree Survey (KiDS)-DR4 telescope tiles which is publicly available. See https://kids.strw.leidenuniv.nl/DR4/index.php

The cutouts have size (36,36,4).
This means, 36 pixels in x and y-direction of image with number of channels=4. 
1 pixel=0.2 arcsec in KiDS-DR4.

All cutouts are made by using the following code and is publicly available now, https://github.com/Anjithajm/cutout
