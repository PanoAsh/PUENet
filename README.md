# Predictive Uncertainty Estimation for Camouflaged Object Detection

------

# Introduction

Uncertainty is inherent in machine learning methods, especially those for camouflaged object detection aiming to finely segment the objects concealed in background. The strong “center bias” of the training dataset leads to models of poor generalization ability as the models learn to find camouflaged objects around image center, which we define as “model bias”. Further, due to the similar appearance of camouflaged object and its surroundings, it is difficult to label the accurate scope of the camouflaged object, especially along object boundaries, which we term as “data bias”. To effectively model the two types of biases, we resort to uncertainty estimation and introduce predictive uncertainty estimation technique, which is the sum of model uncertainty and data uncertainty, to estimate the two types of biases simultaneously. Specifically, we present a predictive uncertainty estimation network (PUENet) that consists of a Bayesian conditional variational auto-encoder (BCVAE) to achieve predictive uncertainty estimation, and a predictive uncertainty approximation (PUA) module to avoid the expensive sampling process at test-time. Experimental results show that our PUENet achieves both highly accurate prediction, and reliable uncertainty estimation representing the biases within both model parameters and the datasets.

:running: :running: :running: ***KEEP UPDATING***.

------

# Model Architecture

<p align="center">
    <img src="./figures/fig_model.jpg"/> <br />
    <em> 
    Figure 1: The structures of our “Bayesian conditional variational auto-encoder” (BCVAE) based COD network, and the “predictive uncertainty approximation” (PUA) module. SAM denotes “selective attention module”. D-ASPP means the “DenseASPP block”. Fusion is “residual convolutional fusion block” from MiDaS(https://github.com/isl-org/MiDaS). “z” denotes latent variables of prior or posterior distribution models.
    </em>
</p>

------

# Performance

<p align="center">
    <img src="./figures/fig_performance_quan.jpg"/> <br />
    <em> 
    Figure 2: Performance comparison with state-of-the-art COD models. * denotes models trained on multi-scale.
    </em>
</p>

<p align="center">
    <img src="./figures/fig_performance_qual.jpg"/> <br />
    <em> 
    Figure 3: Visual results of our PUENet and the competing models. “predictive uncertainty approximation” (PUA) module provides “σa2”, which approximates the sampling based predictive uncertainty, i.e., “σe2”.
    </em>
</p>

------

# Implementation

The codes are publicly available, please contact yi.panoash@gmail.com for download link.

The training and testing datasets can be downloaded at [COD10K-train](https://drive.google.com/file/d/1D9bf1KeeCJsxxri6d2qAC7z6O1X_fxpt/view), [COD10K-test + CAMO-test + CHAMELEON](https://drive.google.com/file/d/1QEGnP9O7HbN_2tH999O3HRIsErIVYalx/view) and [NC4K](https://drive.google.com/file/d/1kzpX_U3gbgO9MuwZIWTuRVpiB7V6yrAQ/view), respectively.

The results of our PUENet are available at [PUENet-model] and [PUENet-predictions].

