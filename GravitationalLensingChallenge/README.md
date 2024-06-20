# Strong Lensing Challenge

![Lensing illustration](https://github.com/ML4SCI/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/gitimage.jpg)

> Illustration by Sandbox Studio, Chicago with Ana Kova

### Description

Since its discovery via its gravitational interactions over half a century ago, the identity of dark matter has yet to be found. This is despite countless experiments aimed at detection of the most promising dark matter candidates. An alternative to terrestial detection (for example, with colliders or liquid xenon) for dark matter identification is unique gravitational signatures which arise from disparte substructure predicitions among dark matter models. Example substructures include subhalos of WIMP-like cold dark matter and vortices of superfluid dark matter. Perhaps the most promising method to infer the unique morphology of these substructures is with strong galaxy-galaxy lensing images; an intermediate dark matter halo (which contains a visible galaxy) lenses a galaxy which is behind it. With this in mind, in these challenges we will use simulated strong lensing images and supervised machine learning models to study the morphogy of dark matter substructure. 

#### Challenge 1 - Multi-Class Classification

In this challenge, we focus on exploring the potential of supervised classification models in identifying dark matter based on simulated strong lensing images with different substructure.

#### Challenge 2 - Image Super-Resolution

In this challenge we will use regression to measure the total fraction of mass in substructure of a dark matter halo. We will do so utilizing simulated strong lensing images with subhalo substructure consistent with non-interacting cold dark matter models. 

### Datasets

#### 1. Multi-Class Classification

The [Dataset](https://drive.google.com/file/d/1GKLETkPWy_uOwfR3UMW8YEQC4lkJa45h/view?usp=sharing) consists of three classes, strong lensing images with no substructure, CDM (cold dark matter) substructure, and axion substructure. The images have been normalized using min-max normalization, but you are free to use any normalization or data augmentation methods to improve your results.

#### 2. Image Super-Resolution

The [Dataset](https://drive.google.com/file/d/1lUOGo2B0Rhxwj_TGZSVEdZJ79GdI7awa/view?usp=sharing) consists of high-resolution (HR) and low-resolution (LR) pairs of strong gravitational lensing images.

### Evaluation Metrics

#### 1. Multi-Class Classification

* ROC curve (Receiver Operating Characteristic curve) and AUC score (Area Under the ROC Curve)  

#### 2. Image Super-Resolution

* MSE (Mean Squared error), SSIM (Similarity Index), and PSNR (Signal to Noise Ratio)

The model performance will be tested on the hidden test dataset based on the above metrics.

### Deliverables

* You are required to submit a Google Colab Jupyter Notebook clearly showing your implementation along with the above-mentioned evaluation metrics for the validation data.
* You must also submit the final trained model, including the model architecture and the trained weights ( For example: HDF5 file, .pb file, .pt file, etc. )

You can use the example notebooks provided in this repository as a template for your work.

### Example Notebooks

#### 1. Multi-Class Classification

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//pranath-reddy/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-Classification.ipynb)

#### 2. Image Super-Resolution

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//pranath-reddy/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-SuperRes.ipynb)

### Contributors

* Sergei Gleyzer<sup>1</sup>
* Michael Toomey<sup>2</sup>
* Pranath Reddy<sup>3</sup>

<sup>1</sup>Department of Physics & Astronomy, University of Alabama, Tuscaloosa, AL 35401, USA

<sup>2</sup>Center for Theoretical Physics, Massachusetts Institute of Technology, Cambridge, MA 02139, USA

<sup>3</sup>University of Florida, Gainesville, FL 32611, USA
