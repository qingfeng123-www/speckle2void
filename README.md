# [Speckle2Void: Deep Self-Supervised SAR Despeckling with Blind-Spot Convolutional NeuralNetworks](https://arxiv.org/abs/2007.02075)

Speckle2Void is a self-supervised Bayesian despeckling framework that enables direct training on real SAR images. This method bypasses the problem of training a CNN on synthetically-speckled optical images, thus avoiding any domain gap and enabling  learning of features from real SAR images. 

This repository contains python/tensorflow implementation of Speckle2Void, trained and tested on the TerraSAR-X dataset provided by ESA [archive](https://tpm-ds.eo.esa.int/oads/access/collection/TerraSAR-X).


BibTex reference:
```
@ARTICLE{2020arXiv200702075B,
       author = {{Bordone Molini}, Andrea and {Valsesia}, Diego and {Fracastoro}, Giulia and
         {Magli}, Enrico},
        title = "{Speckle2Void: Deep Self-Supervised SAR Despeckling with Blind-Spot Convolutional Neural Networks}",
      journal = {arXiv e-prints},
     keywords = {Electrical Engineering and Systems Science - },
         year = 2020,
        month = jul,
          eid = {arXiv:2007.02075},
        pages = {arXiv:2007.02075},
archivePrefix = {arXiv},
       eprint = {2007.02075},
 primaryClass = {eess.IV}
}
```

#### Setup to get started
Make sure you have Python3 and all the required python packages installed:
```
pip install -r requirements.txt
```


#### Get TerraSAR-X data through ESA EO products online search service and build the dataset.
- Download the TerraSAR-X products from the [ESA EO products online search service](https://tpm-ds.eo.esa.int/oads/access/collection/TerraSAR-X)
- Pre-process the dataset through the speckle decorrelator explained in the paper: [Blind speckle decorrelation for SAR image despeckling](https://ieeexplore.ieee.org/document/6487399). The blind-spot networks work properly if the noise is spatially decorrelated. The SAR imaging system correlates the speckle noise in SAR images during acquisition. A speckle decorrelator is needed before performing despeckling.
    * Convert the downloaded TerraSAR-X SLC products into _.mat_ files as complex SAR images. We need complex SAR data to run the speckle decorrelation procedure. It is advised to save in each _.mat_ file a complex SAR image of size 10000x10000 maximum for performance reasons.

