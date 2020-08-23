## STAR: Sparse Trained Articulated Human Body Regressor 

<!-- TODO: Replace with our arxiv link -->
<!-- [![report](https://img.shields.io/badge/arxiv-report-red)](https://arxiv.org/abs/1912.05656) -->

[[Project Page](https://star.is.tue.mpg.de/)] 
[[Paper](https://ps.is.tuebingen.mpg.de/uploads_file/attachment/attachment/618/star_paper.pdf)]
[[Supp. Mat.](https://ps.is.tuebingen.mpg.de/uploads_file/attachment/attachment/619/star_supmat.pdf)]

<p align="center">
  <img src="./images/main_teaser.png" />
</p>


## Table of Contents
  * [License](#license)
  * [Description](#description)
    * [Content](#content)
    * [Installation and Usage](#Installation)
    * [SMPL Comparison](#SMPLComparison)
  * [Citation](#citation)
  * [Acknowledgments](#acknowledgments)
  * [Contact](#contact)


## License

Software Copyright License for non-commercial scientific research purposes.
Please read carefully the following terms and conditions and any accompanying
documentation before you download and/or use the STAR model and
software, (the "Data & Software"). By downloading and/or using the
Data & Software (including downloading, cloning, installing, and any other use
of the corresponding github repository), you acknowledge that you have read
these terms and conditions, understand them, and agree to be bound by them. If
you do not agree with these terms and conditions, you must not download and/or
use the Data & Software. Any infringement of the terms of this agreement will
automatically terminate your rights under this License


## Description

STAR - A **S**parse **T**rained  **A**rticulated Human Body **R**egressor is a generateive 3D human body model, that is designed to be a drop in replacement for the widely used SMPL model.
STAR is trained on largest dataset of more than 14,000 human body subjects, with a learned set of sparse and spatially local pose corrective 
blend shapes. In the Figure below, a single joint movement only influence a sparse set of the model vertices. The mesh vertices in 
gray are not affected by the joint movement. In contrast to SMPL bending the left elbow causes a bulge in the right elbow.  <br/>
STAR is publicly avaiable with the full 300 principal component shape space for research purposes from our website https://star.is.tue.mpg.de/

<p align="center">
  <img src="./images/sparse_pose_correctives.png" />
</p>


 For more details, please see our ECCV paper
[STAR: Sparse Trained Articulated Human Body Regressor](https://ps.is.mpg.de/uploads_file/attachment/attachment/618/star_paper.pdf).

## Content
This repository contains the model loader in the following frameworks:
* PyTorch. 
* Tensorflow 2.0.
* Chumpy.

Code tested on Python 3.69, CUDA 10.1, CuDNN 7.6.5 and PyTorch 1.6.0, Tensorflow 2.3 , Chumpy 0.69 on Ubuntu 18.04

## Installation 

### Install 
1. Clone the repository: 

```Shell
git clone git@github.com:ahmedosman/STAR.git
```
2. For Chumpy
```
pip install chumpy==0.69
pip install opencv-python
```
3.For PyTorch
```
pip install pytorch==1.6
```
4.For Tensorflow
```
pip install tensorflow-gpu==2.3
```
5. Download the models from [our website][https://star.is.tue.mpg.de/] and update the paths in config.py
6. Update the python path environment variable ($PATH_TO_REPO is the path to the repository on your machine). 
```
export PYTHONPATH=$PYTHONPATH:$PATH_TO_REPO
```

### Usage

Under demos/* there are scripts demonstrating how to load and use the model in all frameworks. 
```bash
    $PATH_TO_REPO/
    ├── demos
    │   │
    │   ├── compare_frameworks.py #Unit test script constructing the model with three frameworks and comparing the output
    │   └── load_chumpy.py        #A script demonstrating loading the model in chumpy
    │   └── load_tf.py            #A script demonstrating loading the model in Tensorflow
    │   └── load_torch.py         #A script demonstrating loading the model in PyTorch
    │   └── profile_tf.py         #A script profiling the STAR graph as a function of batch Size in Tensorflow
    |   └── profile_torch.py      #A script profiling the STAR graph as a function of batch Size in PyTorch
```

## SMPL Comparison 
STAR is designed to be a drop in replacement for SMPL, similar to SMPL it is parameterised with pose and shape parameters. 

<p align="center">
  <img src="./images/smpl_vs_star.jpeg" />
</p>

### STAR Kinematic Tree
<p align="center">
  <img src="./images/star_kinematic_tree.png" />
</p>




## Citation

If you find this Model & Software useful in your research we would kindly ask you to cite:

```bibtex
@inproceedings{STAR:ECCV:2020,
  title = {STAR: Sparse Trained Articulated Human Body Regressor},
  author = {Ahmed A. A. Osman, Timo Bolkart, Michael J. Black},
  booktitle = {European Conference on Computer Vision (ECCV) },
  month = aug,
  year = {2020},
  month_numeric = {8}
}
```

## Acknowledgments
We thank Naureen M. Mahmood, Talha Zaman,  Nikos Athanasiou, Muhammed Kocabas, Nikos Kolotouros and Vassilis Choutas for the discussions 
and Sai Kumar Dwivedi, Lea Muller,  Amir Ahmad and Nitin Saini for proof reading the script and Joachim Tesch for help with game engines plug-ins.
Thanks Mason Landry for the voice over and Benjamin Pellkofer for the IT support.

## Contact

For questions, please contact [star@tue.mpg.de](mailto:star@tue.mpg.de). 

For commercial licensing (and all related questions for business applications), please contact [ps-licensing@tue.mpg.de](mailto:ps-licensing@tue.mpg.de).
