
# Hackathon - NMR Challenge

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ML4SCI/DeepLearnHackathon/blob/main/NMRSpinChallenge/Hackathon_NMR_Challenge_July2024.ipynb)


### Problem Statement

- Nuclear Magnetic Resonance (NMR) is an experimental technique that allows for the control and measurement of nuclear spins in crystals and molecules.
- A common "recipe" for NMR is called the spin echo: the spins start aligned, begin to disperse, and are then refocused. This creates a sharp peak, or "echo", in the net magnetization $M$ of the material at a later time. When the spins interact with each other, this refocused echo can become highly distorted.
- Materials with strong electron-electron couplings have a variety of applications, from superconductivity to ferromagnetism. They also tend to enhance the nuclear spin-spin couplings, allowing NMR to act as a probe of these important systems.
- Design and train a model that predicts the strength and shape of interactions between the nuclear spins from simulated time-dependent magnetization curves, $M(t)$.

Before getting to any code, we first review the structure of this machine<br> learning problem and introduce some of the details of the underlying physics we<br>
are trying to capture.

## Quick description of the ML problem

### Goal:
Predict three numbers from a large input vector of real numbers.

### Example Solution:  Multilayer Neural Network and Decision Trees (see code after this introduction)

To get the complex-valued time-series M(t) into a neural network, we can simply "stack" the real and complex parts together to make a real-valued input vector.

## Deliverables:
* Fill out the pre- and post-hackathon surveys
We ask you to submit two models: one for "gauss" and one for "RKKY". We ask you to make your predictions on the test sets. You don't have the true labels for the test sets meaning you are limited only to what you know about train sets (and validation subsets) to build the best models possible. 

Use your models to predict the three spin-interaction variables from the  echos, and submit your results for **each model** (two models total) in a tab delimited .txt  file of dimensions 6000 x 3 matching the "<model_type>_mat_info_model.txt" format.

That is, the columns should be:
| $\\alpha$ | $\\xi$ | $d$ |
and there should be 6000 rows.

Name this file "<model_type>_mat_info_eval.txt". 
The quality of the model will be judged by the minimization of normalized <br> mean-square error: 
$\\textrm{Err} = \\sum_{v=1}^{3} \\sum_{i=i}^{6000} \\left( \\tilde{v}^i_\\textrm{model} - \\tilde{v}^i_\\textrm{true} \\right)^2 $\n",

where $v^i$ is one of the three spin-interaction variables for echo number $i$, <br>, and the tilde represents normalization of each variable (using the StandardScaler() object used above). Your submission should include: 
- Your ipython notebook (`.ipynb`)
- A PDF copy of your notebook together with a description of what you have done
- Your model's evaluation of the Gaussian data (\"gauss_mat_info_eval.txt\")
- Your model's evaluation of the RKKY data (\"RKKY_mat_info_eval.txt\")

**NOTE: If your final model prediction files aren't named \"gauss_mat_info_eval.txt\" and \"RKKY_mat_info_eval.txt\" your results might not be correctly evaluated by the automatic evaluation software.**

## Introduction to NMR and spin echos

Although the NMR "spin echo" technique may sound complicated, the following <br> animation created by Gavin W Morley (by way of <br>
https://en.wikipedia.org/wiki/Spin_echo) makes it much clearer!


![NMR Spin Echo Animation](https://upload.wikimedia.org/wikipedia/commons/9/9b/HahnEcho_GWM.gif)


The red arrows in this animation represents the values of nuclear spins in the <br>
material.

They all begin in the same direction (up), and then an applied magnetic field<br>
rotates them into the x-y plane (indicated by the 90$^\circ$ pulse).<br>
A constant external magnetic field in the z-direction did not affect the spins <br>
when they were pointing "up", but now that they lie in the x-y plane they begin <br>
to precess.


Because each nuclear spin sits in a slightly different magnetic environment, <br>
each one has a slightly different response to the background z-direction <br> magnetic field, causing some to precess in a clockwise direction and others in <br>
a counterclockwise direction.


After a fixed amount of time, $t$ in the above animation, a second magnetic <br>
pulse is applied and rotates each spin 180$^\circ$ in the x-y plane. <br>
After this, the spins continue to move as they did before, but because of the <br>
180$^\circ$ pulse they are now effectively precessing  "backwards" compared to <br>
the original motion!<br>
So after an additional time $t$ passes, the variations in precession time is <br>
canceled out, causing a refocusing of the spins.

This shows up as a measurable "echo" in the average spin magnetization of the <br>
material, and can be measured in experiments. <br>
This is an important technique because the average spin magnetization is hard <br>
to measure during an applied "pulse", but there is no external pulse during the <br>
"echo", allowing for accurate measurement of the peak value and decay shape.

Here is a typical curve for the time-dependent magnetization $M(t)$ for a <br> spin-echo in most materials:

![standard_spinecho.png](https://raw.githubusercontent.com/ML4SCI/DeepLearnHackathon/main/NMRSpinChallenge/standard_spinecho.png)

Sometimes, a more complicated curve can occur, such as:

![coupled_echo.png](https://raw.githubusercontent.com/ML4SCI/DeepLearnHackathon/main/NMRSpinChallenge/coupled_echo.png)

This more complicated structure has been caused by spin-spin interactions <br>
between the precessing nuclear spins. Normally, each spin precesses in a<br> uniform way irrespective of the rest of the nuclei in the material. In this <br>
coupled case, however, the nuclear magnetization that occurs near the "echo" <br>
influences the spins' motions, modifying the shape of the observed echo.

## Electronic and nuclear spins

Most materials can be classified by their electronic properties into three <br> categories: metal, insulator, and semiconductor. <br>
These terms are based on a semi-classical description of the electrons in a <br>
crystal.<br>
The electrons are treated as a collection of classical particles, with energies <br>
that depend on their momentum in a way determined by the atomic structure of <br> the crystal.

However, there are other electronic phases of matter that are truly "quantum" <br>
and cannot be described accurately with a classical analogy. <Br>
In these scenarios, complicated structures in the electron states can give rise <br>
to large electronic spin density or strong electron-electron coupling. <br>
Because of these strong couplings between electrons, they are often hard to <br>
probe experimentally.

Luckily, electrons can interact with the nuclear spins of a material (by way of <br> the hyperfine-interaction).<br>
If the electron-nuclear coupling becomes strong enough, then a non-neglible <br>
two-step process can couple the nuclei with each other throughout the material. <br>
That two-step process is when a nuclear spin couples to an electron and changes <br>
its motion, and then that electron later "scatters" off another nuclear spin <br>
elsewhere in the material.

We represent this two-step scattering process by way of an effective spin-spin <br>
coupling between a nuclei at position $r_j$ and $r_i$. **There are two datasets,** <br>
**"gauss" and "RKKY", and thus you will have to generate TWO models and hand in** <br> **two models.**


The first is a simple gaussian function ("gauss"):

$T_1(i,j) = \alpha \exp{\left[ \left(\frac{-|r_j - r_i|}{\xi} \right)^{2} \right]}$

And the second is the traditional Ruderman–Kittel–Kasuya–Yosida function <br> ("RKKY"):

$T_2(i,j) = \alpha x^{-4} \left( x \cos{x} - \sin{x} \right)$

with $x = 2 \frac{|r_j - r_i|}{\xi}$


For both function, $\alpha$ is the coupling strength and $\xi$ is the coupling length.

Generally, $\alpha$ and $\xi$ will depend on the details of the nuclear-electron <br>
coupling and the quantum state of the electrons, but here we will sample them <br>
randomly to see if the spin-echo experiment can provide enough information to <br>
accurately "reverse engineer" these values from a single $M(t)$ curve.

Our simulations also include dissipation of the nuclear spins: due to couplings <br>
with the environment the spin information can be "lost". <Br>
This occurs at a time scale $T_\textrm{decay} \simeq \Gamma^{-1/2}$, with $\Gamma$ given by:

$\Gamma = 10^{-d}$

Our goal is to develop two models, one for each function, that accurately <br> determine the above variables ($\alpha$, $\xi$, and $d$) from a single $M(t)$ curve. <br>
Note that RKKY is a harder problem.

## Contributors

- Stephen Carr (Brown Theoretical Physics Center)
- Charles Snider (Brown University)
- J. B. Marston (Brown Theoretical Physics Center)
- V. F. Mitrović (Brown University)
- D. E. Feldman (Brown Theoretical Physics Center)
- C. Ramanathan (Dartmouth College)
- Eric Reinhardt (The University of Alabama)
