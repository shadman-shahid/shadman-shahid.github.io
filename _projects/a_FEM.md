---
layout: page
title: Solution of two dimensional Laplace equation
short-title: FEM method- Laplace equation
description: A simple MATLAB code to solve 2D Laplace equation with FEM method  
img: assets/img/project/fem_n.jpg
importance: 8
category: academic
---

<div style="text-align: justify;">
The finite element method (FEM) is the workhorse behind most commercial electromagnetic solvers, and the best way to understand it is to build one. In this project, a 2D FEM solver is written from scratch in MATLAB to solve the Laplace equation over the cross-section of a microstrip transmission line - a metal strip carrying 5 V, sitting on a GaAs substrate (dielectric constant of 12.9) inside a grounded enclosure. The governing equation is cast into its weak form, and the domain is discretized into first-order triangular elements, over which the potential is assumed to vary linearly. The element contributions are assembled into a sparse global stiffness matrix, the known potentials on the strip and the outer boundary enter the right-hand side through Dirichlet lifting, and the resulting system of equations is solved directly. From the solution, the potential distribution and the vector electric field over the cross-section are obtained; both for a single microstrip and for a coupled pair of strips driven at +5 V and -5 V.
</div>
<br>
<div style="text-align: justify;">
A major focus of the project was validating the hand-assembled solver against the MATLAB PDE Toolbox. On identical meshes, the two agree to machine precision (~1e-13 V), confirming that the assembly and boundary treatment are exact. The electric field is singular at the corners of the strip, which makes pointwise comparison a poor error metric; instead, the stored field energy (equivalently, the line capacitance) is used, which converges at the theoretically expected rate for such corner singularities. From the extrapolated energies, the line parameters of the structure are extracted - a capacitance of 69.5 pF/m, an effective permittivity of 4.95 and a characteristic impedance of 106.9 &Omega;. Finally, the solver is benchmarked on a standard open microstrip geometry against the closed-form Hammerstad-Jensen model, where the computed effective permittivity, characteristic impedance and capacitance all agree to within 1%.
</div>

<iframe src="/assets/pdf/fem2D_laplace.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/fem2D_laplace.pdf">Download PDF</a>.
</iframe>

<div style="text-align: justify;">
<b>*The codes and necessary files are available at <a href="https://github.com/shadman-shahid/2D_FEM_solver">Github</a>.</b>
</div>
