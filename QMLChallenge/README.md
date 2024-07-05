# QML Challenge

<div align = "center">
  <img width='auto' height=350 src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvFhfnoZf8qGq5B77keDh_bmSfdpSsd_MJXehTGKQOkfl4uUgBZ3fM8d0kjjcCGDfYDXwYzPpZf5moACKyK2Ejew-ldNRvAofzhHQXGTRYmJgHatvbLTR1nqXotI-QZj2sNVao87w5B6g/s1600/quantum+model.png">
  <img width='auto' height=350 src="https://prefetch.eu/know/concept/bloch-sphere/sketch-full.png?v=1">
</div>

The goal of the challenge is to use a quantum machine learning model to perform anomaly detection on a particle physics dataset.
The idea is to train a model on background data only. Afterwards, we want to use the model to separate signal and background events in a test dataset.


## Dataset

We provide simulated detector images of quark and gluon jets for the dataset. To reduce the computational burden, we reduced the images to the size `30x30`. The dataset can be obtained [here](https://drive.google.com/file/d/1dJiFRqMWhBzT6lS7neGrIBYEiYX8oveT/view?usp=sharing).

The images show jets which originate from a Quark or Gluons. The Quark-initiated jets are labelled as $1$, while the Gluon-initiated jets are labelled as $0$. We want to train on the Quark-initiated jets and then tag the gluon jets.

Some example samples are shown below:
<div align = "center">
  <img width='auto' height=350 src="./dataset.png">
</div>

The top row shows the quark-initiated jets, while the bottom row shows gluon-initiated jets.

## Model

You are free to choose any model you like. However, in the spirit of quantum machine learning, we put a limit on the maximum number of parameters you are allowed to use.

## Challenge and Evaluation

We evaluate the challenge on the AUC of a black box test set. To be considered for the challenge, a solution needs to satisfy the following criteria:

1. The model is trained only on Quark jets (label 1)
2. The quantum circuit should not use more than 20 qubits.
3. The solution is submitted as an executable notebook where which can be run without any additional third party libraries.

## Example notebook

We provide an example notebook which shows how to load the dataset and evaluate the performance of an anomaly detection model:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ML4SCI/DeepLearnHackathon/blob/qml/QMLChallenge/QMLChallenge.ipynb)

In the example above, we train a __classical__ autoencoder. An example of a quantum autoencoder on the MNIST dataset is provided in the notebook `QMLChallenge_QAE.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ML4SCI/DeepLearnHackathon/blob/qml/QMLChallenge/QMLChallenge_QAE.ipynb).

To learn more about QML, checkout the official [demos](https://pennylane.ai/qml/demonstrations/) by PennLane.

image courtesy: [tensorflow](https://blog.tensorflow.org/2020/03/announcing-tensorflow-quantum-open.html), [prefetch](https://prefetch.eu/know/concept/bloch-sphere/).

## Tips for working with Google Colaboratory

To use the dataset with Google Drive in Google Colab, follow the steps below:
- After opening the dataset link, click "Add shortcut to drive".
- Click the "All locations" tab and add it to "My Drive".

The code to mount Google Drive is present in `QMLChallenge.ipynb`

Additional Python packages can be installed using the `!` operator as shown in the example notebooks.

## Contributors

- Sergei Gleyzer (Department of Physics & Astronomy, University of Alabama)
- Tom Magorsch (TUM School of Natural Sciences, Physics Department, Technical University of Munich)
- Gopal Ramesh Dahale (Indian Institute of Technology Bhilai)
