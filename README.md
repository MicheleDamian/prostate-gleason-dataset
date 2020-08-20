[![prostate-cancer-dataset release](https://raster.shields.io/badge/release-v0.1-blue?style=plastic)](https://github.com/MicheleDamian/prostate-cancer/releases)
[![prostate-cancer-dataset size](https://raster.shields.io/badge/size-1.8G-blue?style=plastic)](https://github.com/MicheleDamian/prostate-cancer/releases)

[![prostate-cancer-dataset license](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0)


# Prostate Gleason Dataset
---

***[add example images]***

*Prostate Gleason Dataset* is an image database of prostate cancer biopsies derived from the [PANDA dataset](https://www.kaggle.com/c/prostate-cancer-grade-assessment/overview). The database consists of about **50K patches** of size **256x256 pixels** extracted from the PANDA's biopsies without overlap. Each patch is associated to a [Gleason grade](https://en.wikipedia.org/wiki/Gleason_grading_system). The patches are grouped in **4 classes** (Background + Stroma + Gleason 0, 1, 2; Gleason 3; Gleason 4; Gleason 5) with the following distribution:

```python
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt

train = pd.read_csv('train.csv')
test = pd.read_csv('test.csv')
train_cnt = train.groupby('gleason').count()
test_cnt = test.groupby('gleason').count()

f, (ax0, ax1) = plt.subplots(1, 2)
sns.distplot(train_cnt, ax=ax0)
sns.distplot(test_cnt, ax=ax1)
```

***[add class distibution]***

My hope is to help improving ML-based prostate-cancer assessment by providing a novel patch labelled dataset. 

Current computational pathology is usually based on labels of whole slide images of biopsies where the labels are ISUP grades or Gleason composite scores. These labels tend to be noisy and non-informative at the cellular/glandular level, for they provide information derived from large, non-contigous and non-omogeneous (w.r.t. the cellular/glandular visual properties of the cancer) areas of the biopsies. 

Tipically, modelling this data for predicting the ISUP grade/Gleason score involves 2 steps: 
 1. finding a relationship between the given whole-slide label and the visual properties of the cancer at the cellular/glandular level; 
 2. tranforming this low-level properties back into a whole-slide prediction. 
 
The *Prostate Gleason Dataset* aims to easy the computational burden on step 1) by providing finer grained labels. 


## Parent Dataset Overview
---


## Derivation Process
---


## Dataset Stats
---

***[log hist patches per biopsy]***


## Models
---


***[efficientNet]***

***[resNet]***

***[resNext]***


## Limitations and Future Work
---

