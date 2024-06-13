# Strong Lensing Challenge

![Lensing illustration](https://github.com/ML4SCIHackathon/ML4SCI/blob/main/GravitationalLensingChallenge/gitimage.jpg)

> Illustration by Sandbox Studio, Chicago with Ana Kova

### Description

Since its discovery via its gravitational interactions over half a century ago, the identity of dark matter has yet to be found. This is despite countless experiments aimed at detection of the most promising dark matter candidates. An alternative to terrestial detection (for example, with colliders or liquid xenon) for dark matter identification is unique gravitational signatures which arise from disparte substructure predicitions among dark matter models. Example substructures include subhalos of WIMP-like cold dark matter and vortices of superfluid dark matter. Perhaps the most promising method to infer the unique morphology of these substructures is with strong galaxy-galaxy lensing images; an intermediate dark matter halo (which contains a visible galaxy) lenses a galaxy which is behind it. With this in mind, in these challenges we will use simulated strong lensing images and supervised machine learning models to study the morphogy of dark matter substructure. 

#### Challenge 1 - Multi-Class Classification

In this challenge, we focus on exploring the potential of supervised classification models in identifying dark matter based on simulated strong lensing images with different substructure.

#### Challenge 2 - Regression

In this challenge we will use regression to measure the total fraction of mass in substructure of a dark matter halo. We will do so utilizing simulated strong lensing images with subhalo substructure consistent with non-interacting cold dark matter models. 

### Datasets

#### 1. Multi-Class Classification

The [Dataset](https://drive.google.com/file/d/1B_UZtU4W65ZViTJsLeFfvK-xXCYUhw2A/view?usp=sharing) consists of three classes, strong lensing images with no substructure, subhalo substructure, and vortex substructure. The images have been normalized using min-max normalization, but you are free to use any normalization or data augmentation methods to improve your results.

#### 2. Regression

The [Dataset](https://drive.google.com/file/d/1hu472ALwGPBcTCXSAM0VoCWmTktg9j-j/view?usp=sharing) consists of strong lensing images for cold dark matter with subhalo substructure. For each lensing image the corresponding fraction of mass in dark matter substructure is provided.

### Evaluation Metrics

#### 1. Multi-Class Classification

* ROC curve (Receiver Operating Characteristic curve) and AUC score (Area Under the ROC Curve)  

#### 2. Regression

* MAE (Mean absolute error)

The model performance will be tested on the hidden test dataset based on the above metrics.

### Deliverables

* You are required to submit a Google Colab Jupyter Notebook clearly showing your implementation along with the above-mentioned evaluation metrics for the validation data.
* You must also submit the final trained model, including the model architecture and the trained weights ( For example: HDF5 file, .pb file, .pt file, etc. )

You can use the example notebooks provided in this repository as a template for your work.

### Example Notebooks

#### 1. Multi-Class Classification

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//ML4SCI/ML4SCIHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-Classification.ipynb)

#### 2. Regression

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//ML4SCI/ML4SCIHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-Regression.ipynb)

### Contributors

* Sergei Gleyzer<sup>1</sup>
* Michael Toomey<sup>2,3</sup>
* Pranath Reddy<sup>4</sup>
* Yurii Halychanskyi<sup>5</sup>

<sup>1</sup>Department of Physics & Astronomy, University of Alabama, Tuscaloosa, AL 35401, USA

<sup>2</sup>Brown Theoretical Physics Center, Providence, RI 02912, USA

<sup>3</sup>Department of Physics, Brown University, Providence, RI 02912, USA

<sup>4</sup>Birla Institute of Technology & Science, Pilani - Hyderabad Campus, Telangana, India

<sup>5</sup>Paul G. Allen School of Computer Science & Engineering, University of Washington, Seattle, WA 98195, USA

