# A spectrum of nonsense-mediated mRNA decay efficiency along the degree of mutational constraint

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.13918125.svg)](https://doi.org/10.5281/zenodo.13918125)

## Overview
A landmark study has proposed several factors on nonsense-mediated mRNA decay (NMD) efficiency using matched genome and transcriptome data of human cancer but was highly affected by random variance caused in measuring the NMD efficiency. In this study, using a more precise, allele-specific expression-based measure of NMD efficiency, a more accurate NMD efficiency model was developed. Combining this model with the public germline variant database stratified by allele frequency, we showed a spectrum of NMD efficiency, from common variants to somatic variants in the cancer genome. 
This software package was used for the training the NMD efficiency model from the TCGA data. The final training set is included in this package and the whole procedure including univariate analysis, correlation analysis, model training, and peformance validation can be demonstrated.

## Software requirements

### Hardware requirements
The provided code requires only a standard computer with enough RAM to support the in-memory operations.

### Software requirements

This package is supported for macOS, Windows, and Linux. The package has been tested on the following systems:
- macOS: Monterey(12.4)
- Windows10


### Python Dependencies
The provided code mainly depends on the Python scientific stacks.

```
NumPy == 1.23.5
pandas == 1.5.2
scikit-learn == 1.2.2
scipy == 1.9.3
pickle
```

## Installation guide
Ob a standard computer, installation time is expected around 5 ~ 10 mins.

### Install from pip
To install all the requirements, run the following command:
```
python -m pip install -r requirements.txt
```

### Install from conda
If you install the Anaconda Distribution, you will already have hundreds of packages installed. If you need to install a package, use
```
conda install <package-name>
```

## Demo and Instructions for use
We provide related codes through Jupyter Notebooks. 
```
jupyter notebook
```
The train.ipynb includes codes related to RFR training from the included training data. Execution of all codes in train.ipynb results in the generation of prediction model file. 

The demo.ipynb can be run after the execution of train.ipynb. 
Based on the prediction model generated from the train.ipynb, funtions that can predict NMD efficiency for a single and a list of data can be run. 
Expected run time for demo on a desktop computer is within one minute

```
def predict_NMD_efficiency(downstream_exon_count:int, last_exon:int,
                           PTC_to_start_codon:int, dist_to_stop_codon:int, PTC_exon_length:int,
                           PTC_to_intron:int, upstream_exon_count:int, cDNAcnt:int, 
                           mRNA_half_life:float, c50nt_to_last_EJ:int, LOEUF:float, AF:float) -> float:
```

The analysis.ipynb includes other analyses performed in the manuscript including univariate analysis and correlation analysis.

The validation_MMRF_TARGET.ipynb includes the analyses using an independent datset, MMRF-TARGET datset as a test data.

