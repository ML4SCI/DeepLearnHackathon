# Exoplanet Search Challenge:
## Detecting Exoplanets in Protoplanetary Disks

![HL Tau](https://github.com/ML4SCI/DeepLearnHackathon/blob/main/ExoplanetSearchChallenge/hl_tau_ALMA.jpeg) (Credit: ALMA (ESO/NAOJ/NRAO))

### Description
Protoplanetary disks are the sites of planet formation. They provide laboratories against which theories of planet formation can be tested. State-of-the-art telescopes have the power to observe these systems in unprecedented detail. These observations can contain a wealth of information that can be used to advance theories. However, extracting this information can be difficult since the observations are noisy, and there are few well-understood disks. Recently, the interplay of advanced simulations and machine learning have been successful in analyzing these disks and identifying exoplanets [[1](https://ui.adsabs.harvard.edu/abs/2021ApJ...920....3A/abstract)] [[2](https://ui.adsabs.harvard.edu/abs/2022MNRAS.510.4473Z/abstract)] [[3](https://ui.adsabs.harvard.edu/abs/2022ApJ...941..192T/abstract)] [[4](https://ui.adsabs.harvard.edu/abs/2023ApJ...947...60T/abstract)]. This promising avenue of research is the basis for this Hackathon challenge.

### Task
The task is to train a model that is capable of identifying if a synthetic observation contains a planet. This is a binary classification proble: planet or no planet.

### Datasets
The data used was generated for [Terry et al. (2022)](https://ui.adsabs.harvard.edu/abs/2022ApJ...941..192T/abstract). It consists of .fits files that represent synthetic continuum observations of protoplanetary disks at 1250 microns. Each simulation, for which there may be several snapshots, consists of a disk with between 0-4 planets. It can be found [here](https://drive.google.com/drive/folders/1wSCaQ2N2w_DmoCc5gyR0C0BP37NNP0S6?usp=sharing).

### Evaluation Metrics
* AUC for withheld test set
* Performance on real observations

## Deliverables
* You are required to submit a Google Colab Jupyter Notebook clearly showing your implementation along with the above-mentioned evaluation metrics for the validation data.
* You must also submit the final trained model, including the model architecture and the trained weights ( For example: HDF5 file, .pb file, .pt file, etc. ) that can be easily implemented on our withheld set.

You can use the example notebooks provided in this repository as a template for your work.

### Example Notebooks

Made locally, but waiting for data upload to complete for Colab