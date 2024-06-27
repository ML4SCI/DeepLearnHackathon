# Strong Lensing Challenge

![Lensing illustration](https://github.com/ML4SCI/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/gitimage.jpg)

> Illustration by Sandbox Studio, Chicago with Ana Kova

### Description

Since its discovery via its gravitational interactions over half a century ago, the identity of dark matter has yet to be found. This is despite countless experiments aimed at detection of the most promising dark matter candidates. An alternative to terrestial detection (for example, with colliders or liquid xenon) for dark matter identification is unique gravitational signatures which arise from disparte substructure predicitions among dark matter models. Example substructures include subhalos of WIMP-like cold dark matter and vortices of superfluid dark matter. Perhaps the most promising method to infer the unique morphology of these substructures is with strong galaxy-galaxy lensing images; an intermediate dark matter halo (which contains a visible galaxy) lenses a galaxy which is behind it. With this in mind, in these challenges we will use simulated strong lensing images and supervised machine learning models to study the morphogy of dark matter substructure. Specifically, we will be looking at two different tasks: multi-class image classification and single-image super resolution.

*Note: You are not required to work on both tasks; you can pick the one that interests you the most.*

#### Task A - Multi-Class Classification

In this task, we will develop and train supervised classification models to identify different types of dark matter substructures in simulated strong lensing images. The goal is to classify the images into three categories: no substructure, CDM (cold dark matter) substructure, and axion substructure. Participants can use various machine learning techniques and are encouraged to experiment with different data preprocessing and augmentation methods to improve model performance.

#### Task B - Image Super-Resolution

In this task, we will develop and train a super-resolution model to enhance the quality of low-resolution strong gravitational lensing images. The goal is to upscale noisy and blurry images to higher resolutions, improving their clarity and detail. Participants can explore different super-resolution techniques, including convolutional neural networks (CNNs), generative adversarial networks (GANs), and other deep learning approaches.

### Datasets

#### A. Multi-Class Classification

The [Dataset](https://drive.google.com/file/d/1GKLETkPWy_uOwfR3UMW8YEQC4lkJa45h/view?usp=sharing) consists of three classes, strong lensing images with no substructure, CDM (cold dark matter) substructure, and axion substructure. The images have been normalized using min-max normalization, but you are free to use any normalization or data augmentation methods to improve your results.

#### B. Image Super-Resolution

The [Dataset](https://drive.google.com/file/d/1lUOGo2B0Rhxwj_TGZSVEdZJ79GdI7awa/view?usp=sharing) consists of high-resolution (HR) and low-resolution (LR) pairs of strong gravitational lensing images.

### Evaluation Metrics

#### A. Multi-Class Classification

* ROC curve (Receiver Operating Characteristic curve) and AUC score (Area Under the ROC Curve)  
* Accuracy, Precision, Recall, and F1 Score  

#### B. Image Super-Resolution

* MSE (Mean Squared error), SSIM (Similarity Index), and PSNR (Signal to Noise Ratio)

Model performance will be assessed on a hidden test dataset using the above metrics. More details about these metrics and the code to calculate them are shared in the example notebooks below.

### Deliverables

* You are required to submit a Google Colab Jupyter Notebook clearly showing your implementation along with the above-mentioned evaluation metrics for the validation data.
* You must also submit the final trained model, including the model architecture and the trained weights ( For example: HDF5 file, .pb file, .pt file, etc. )

You can use the example notebooks provided in this repository as templates for your work. While the notebooks use PyTorch, you are free to use any other machine learning or deep learning frameworks such as TensorFlow or Scikit-Learn.

### Example Notebooks

#### A. Multi-Class Classification

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//pranath-reddy/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-Classification.ipynb)

#### B. Image Super-Resolution

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github//pranath-reddy/DeepLearnHackathon/blob/main/GravitationalLensingChallenge/StrongLensingChallenge-SuperRes.ipynb)

### Getting Started

To get started with the challenge, follow these steps:

1. **Explore the example notebooks**: Open the example notebooks in Google Colab to understand the workflow and get a head start on your implementation.
2. **Download the datasets**: If you plan on working on your local machine, download the datasets for both tasks from the provided links and place them in the appropriate directories.
3. **Develop your models**: Use the example notebooks as templates to develop your own models for both tasks. Feel free to experiment with different techniques and approaches.
4. **Submit your work**: Once you have developed and trained your models, submit the Google Colab notebooks and the trained model files as specified in the Deliverables section.

We look forward to reviewing your submissions!

### Contributors

* Sergei Gleyzer<sup>1</sup>
* Michael Toomey<sup>2</sup>
* Pranath Reddy<sup>3</sup>

<sup>1</sup>Department of Physics & Astronomy, University of Alabama, Tuscaloosa, AL 35401, USA

<sup>2</sup>Center for Theoretical Physics, Massachusetts Institute of Technology, Cambridge, MA 02139, USA

<sup>3</sup>University of Florida, Gainesville, FL 32611, USA
