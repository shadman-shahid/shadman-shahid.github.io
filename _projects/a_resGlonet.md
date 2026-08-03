---
layout: page
title: Inverse Design of Thin Film Stacks via a Residual Generative Optimization Network
short-title: Thin Film Inverse Design (Res-GLONet)
description: A generative deep learning model that inverse-designs multilayer thin film stacks to match a target optical response.
img: assets/img/project/ResGloNet.png
importance: 4
category: academic
---

Designing a multilayer dielectric thin film stack to hit a target optical response is normally a slow trial-and-error process, or a computationally expensive sweep with gradient-based optimizers. In this project, I implemented Res-GLONet, a residual generative optimization network, to inverse-design 1D thin film stacks directly from a target reflection or transmission spectrum. The generator, a residual multilayer perceptron network with 16 cascaded residual blocks, takes a random noise vector and outputs the layer thicknesses and a probability distribution over a material library, from which the refractive index of each layer is sampled. This design is fed to a transfer matrix method (TMM) solver, which acts as the discriminator by computing the resulting spectrum and the loss against the target response.
{: style="text-align: justify;"}


Since the reference TMM implementation was written in NumPy, I reimplemented and vectorized it in PyTorch using scattering matrices, so the solver could sit inside the network's computation graph and backpropagate gradients directly, batched across devices, wavelengths and incidence angles. I also found and corrected a sign error in the published loss function that would otherwise cause training to diverge. The model was tested on two designs: a 3-layer anti-reflection coating, which converged to an average reflectivity of about 2.1% (within 1% of the benchmark paper's results), and a 50-100 layer narrowband transmission filter targeting sharp transmission peaks at 850 nm and 870 nm, drawn from a 7-material library, which converged to about 10% mean squared error. Both designs converged within about 10 minutes on a personal laptop with a modest GPU, with PCA plots of the design space showing the generated samples collapsing from a broad random spread down to a tight cluster near the optimum over the course of training.
{: style="text-align: justify;"}
<br>
<iframe src="/assets/pdf/EEE_6609_Project_Report.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/EEE_6609_Project_Report.pdf">Download PDF</a>.
</iframe>
