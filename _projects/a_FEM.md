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
The finite element method (FEM) powers most commercial electromagnetic solvers, and building one is the best way to understand it. This project implements a 2D FEM solver from scratch in MATLAB, solving the Laplace equation over a microstrip transmission line: a metal strip carrying 5 V on a GaAs substrate (dielectric constant 12.9) inside a grounded enclosure. The equation is cast into weak form, and the domain is meshed with first-order triangular elements, over which the potential varies linearly. Element contributions are assembled into a sparse global stiffness matrix, boundary potentials are applied via Dirichlet lifting, and the system is solved directly. The solver outputs the potential and electric field for both a single microstrip and a coupled pair driven at +5 V and -5 V.
</div>
<br>
<div style="text-align: justify;">
The solver was validated against the MATLAB PDE Toolbox. On identical meshes, the two agree to within ~1e-13 V, confirming the assembly and boundary treatment are exact. Since the electric field is singular at the strip corners, pointwise comparison is a poor error metric. Instead, stored field energy (equivalently, line capacitance) is used, which converges at the expected rate for corner singularities. The extrapolated energies give a capacitance of 69.5 pF/m, an effective permittivity of 4.95, and a characteristic impedance of 106.9 &Omega;. The solver was also benchmarked against the closed-form Hammerstad-Jensen model on a standard open microstrip, agreeing to within 1% on all three parameters.
</div>
<br>
<iframe src="/assets/pdf/fem2D_laplace.pdf" width="100%" height="600px" frameborder="0">
    Your browser does not support PDFs. Please download the PDF to view it: <a href="/assets/pdf/fem2D_laplace.pdf">Download PDF</a>.
</iframe>

<div style="text-align: justify;">
<b>*The codes and necessary files are available at <a href="https://github.com/shadman-shahid/2D_FEM_solver">Github</a>.</b>
</div>
