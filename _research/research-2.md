---
title: 'Code implementation'
excerpt: "Short description of portfolio item number 2 <br/><img src='/images/500x300.png'>"
collection: research 
---

The birth of Gmunu ([DOI](http://dx.doi.org/10.1088/1361-6382/ab8e9c))
------
Numerical relativity is the essential tool for simulating astrophysical systems at extreme gravity.
Einstein equations in dynamical simulations are conventionally solved with hyperbolic free-evolution schemes such as the so-called BSSN, conformally and covariant Z4 (CCZ4), and Z4c schemes.
However, these schemes may not suitable for ultra-long term simulations, the constraint equations will be largely violated eventually due to accumulating numerical errors.
Alternatively, constrained-evolution formulation is theoretically more favourable by promising more stable and accurate simulations. 
Nevertheless, such an approach is not widely used because the computational cost of solving the elliptic-type constraint equations during the evolution is in general significantly higher than hyperbolic free-evolution schemes. 
Therefore, time constraint and heavy demand for computational resources become the greatest barriers that prevent the progress in constrained-evolution scheme simulations.

To overcome the difficulties aforementioned, I have constructed Gmunu, the General-relativistic multigrid numerical solver.
With Gmunu, as the first step, Einstein equations are solved in the constrained-evolution formulation under the conformally flat condition (CFC) approximation using multigrid method.
In this work, for the ever first time, I have shown that cell-centred multigrid-based metric solver can not only naturally couple with finite-volume based hydrodynamics solver, but also robustly solve the highly non-linear metric equations.
Moreover, I have demonstrated that with multigrid acceleration, one can solve the metric equations on a comparable timescale as solving the hydrodynamics equations.
Gmunu is the first, so far the only, code that adopts multigrid metric solver in the dynamical GR(M)HD simulations.

Framework enhancement of Gmunu ([DOI](10.1093/mnras/stab2606))
------
Depending on the nature of the astrophysical scenarios considered, different coordinate systems could be used to capture the physics and information better.
Also, the lengthscales and timescales involved in different parts of the systems typically differ by several orders of magnitude.
Hence, to numerically model these systems accurately within a reasonable time and affordable computational resources, a parallelised, multi-scale and multi-dimensional code that supports various curvilinear geometries is the panacea.
Such general-relativistic code with dynamical spacetime had been lacking, until the enhancement of Gmunu.

After discovering and showing the great potential of the multigrid-based constrained-evolution scheme in the previous work, I decided to bring Gmunu to a more advanced level through enhancement to make it capable of a wider range of astrophysical studies.
In this upgraded version, Gmunu is able to solve general-relativistic magnetodynamics (GRMHD), has been fully parallelised with Message Passing Interface (MPI), and affords the flexibility of choosing dimensions and coordinates (i.e. Cartesian, cylindrical and spherical) with the efficient block-based adaptive mesh refinement (AMR) module.
In this work, I have presented the first elliptical divergence cleaning to guarantee the absence of magnetic monopoles during the GRMHD evolution by using multigrid method.
Moreover, I have demonstrated the superior robustness of Gmunu, where the code is able to evolve different kinds of extreme neutron stars for a long period of time in different dimensions and coordinates, catering to users with different needs.

This enhancement transforms Gmunu from an axisymmetric prototype to a practical and powerful numerical infrastructure for astrophysics.

Resistive MHD extension of Gmunu ([DOI](10.3847/1538-4365/ac6cec))
------
Assuming vanishing electrical resistivity prevents some important physical processes such as dissipation and magnetic reconnection.
Magnetic reconnection can not only change the magnetic field's topology, but also convert magnetic energy into other forms of energy such as heat and kinetic energy within very short time-scales.
These processes, although usually occurring at very small length-scales, could significantly affect the large scale dynamics of the plasmas.

The resistive GRMHD has been included recently in Gmunu.
When the resistivity is realistically small but finite, the dynamical time-scales of the electric field are much shorter than the MHD evolution, resulting in a stiff relaxation term in Ampere's law.
Applying explicit time integration would be inefficient due to the extremely strict constraints on the time steps.
Acknowledging such shortcomings, I have implemented implicit-explicit Runge-Kutta schemes.
Moreover, in this work, I have compared the performances and properties of three divergence-free handling approaches in neutron star modellings.
They are 
1. hyperbolic cleaning through a generalised Lagrange multiplier; 
2. constrained transport schemes and 
3. elliptic cleaning by means of multigrid solver.

In this work, I have shown that combining staggered constrained transport scheme with elliptic cleaning could significantly suppress the amplitude of the ``magnetic monopoles'', and is expected to enable ultra-long accurate MHD simulations.

