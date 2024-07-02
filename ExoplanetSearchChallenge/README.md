# Exoplanet Search Challenge:
## Detecting Exoplanets in Protoplanetary Disks

![HL Tau](https://github.com/ML4SCI/DeepLearnHackathon/blob/main/ExoplanetSearchChallenge/hl_tau_ALMA.jpeg)

Credit: ALMA (ESO/NAOJ/NRAO)

### Description
Protoplanetary disks are the sites of planet formation. They provide laboratories against which theories of planet formation can be tested. State-of-the-art telescopes have the power to observe these systems in unprecedented detail. These observations can contain a wealth of information that can be used to advance theories. However, extracting this information can be difficult since the observations are noisy, and there are few well-understood disks. Recently, the interplay of advanced simulations and machine learning have been successful in analyzing these disks and identifying exoplanets [[1](https://ui.adsabs.harvard.edu/abs/2021ApJ...920....3A/abstract)] [[2](https://ui.adsabs.harvard.edu/abs/2022MNRAS.510.4473Z/abstract)] [[3](https://ui.adsabs.harvard.edu/abs/2022ApJ...941..192T/abstract)] [[4](https://ui.adsabs.harvard.edu/abs/2023ApJ...947...60T/abstract)]. This promising avenue of research is the basis for this Hackathon challenge.

### Task
The task is to train a model that is capable of identifying if a synthetic observation contains a planet. This is a binary classification problem: planet or no planet.

### Datasets
The data used was generated for [Terry et al. (2022)](https://ui.adsabs.harvard.edu/abs/2022ApJ...941..192T/abstract). It consists of .fits files that represent synthetic continuum observations of protoplanetary disks at 1250 microns. Each simulation, for which there may be several snapshots, consists of a disk with between 0-4 planets. Data includes [the full training dataset](https://drive.google.com/file/d/15AMGfgEu2ltGZN3rVtMV97mSbF2USrs6/view?usp=sharing), [a subset of the training data](https://drive.google.com/file/d/1I0JS1Qd896BGgsPcga3umQm-RuJB37UA/view?usp=drive_link), and [the training labels](https://drive.google.com/file/d/1gtBi4ILvCe8nTF09p_E9WWMplTQGC2Wr/view?usp=drive_link). The labels correspond to the simulation number, e.g., planet0_xxxx.fits corresponds to run 0. Each .fits file comes with 4 channels, but only the first one is relevant.

### Evaluation Metrics
* AUC for withheld test set that will not be given
* Performance on real observations

## Deliverables
* You are required to submit a Google Colab Jupyter Notebook clearly showing your implementation along with the above-mentioned evaluation metrics for test data. This test data is part of the provided data, but it should not be used as training or validation data. It is not the same data that we will test on.
* A PDF of your final Jupyter notebook
* You must also submit the final trained model, including the model architecture and the trained weights (For example: HDF5 file, .pb file, .pt file, etc.) that can be easily implemented on our withheld data.

You can use the example notebooks provided in this repository as a template for your work.

### Example Notebooks
An example notebook that will (poorly) solve the challenge using a small subset of data is in this repository and in Google Colab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1qriyMubSylQFI3thT2nYa5getTDD78ea?usp=sharing)

This example only uses the small training subset that is downloaded during runtime since this is meant for speed and clarity rather than performance. Final training should be done on the entire training set. It is recommended that the data be added to your own Google Drive then mounted rather than downloading the data every time. Alternatively, it can be done locally, but training will take a long time without GPUs.