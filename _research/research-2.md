---
title: 'Code implementation'
excerpt: "Short description of portfolio item number 2 <br/><img src='/images/500x300.png'>"
collection: research 
---

Development of Gmunu.

Gmunu 1.0
------
Numerical relativity is the essential tool for simulating astrophysical systems at extreme gravity.
Einstein equations in dynamical simulations are conventionally solved with hyperbolic free-evolution schemes such as the so-called BSSN (by Baumgarte and Shapiro \cite{1999PhRvD..59b4007B}, Shibata and Nakamura \cite{1995PhRvD..52.5428S}), conformally and covariant Z4 (CCZ4) \cite{2003PhRvD..67j4005B}, and Z4c \cite{2010PhRvD..81h4003B} schemes. %fixme: full form
However, these schemes are by construction not suitable for ultra-long term simulations, the constraint equations will be largely violated eventually due to accumulating numerical errors.
Alternatively, constrained-evolution formulation (e.g. \cite{2004PhRvD..70j4007B, 2009PhRvD..79b4017C}) is theoretically more favourable by promising more stable and accurate simulations. 
Nevertheless, such an approach is not widely used because the computational cost of solving the elliptic-type constraint equations during the evolution is in general significantly higher than hyperbolic free-evolution schemes. 
Therefore, time constraint and heavy demand for computational resources become the greatest barriers that prevent the progress in constrained-evolution scheme simulations.

To overcome the difficulties aforementioned, I have constructed \texttt{Gmunu}, the \texttt{G}eneral-relativistic \texttt{mu}ltigrid \texttt{nu}merical solver \cite{2020CQGra..37n5015C}.
With \texttt{Gmunu}, as the first step, Einstein equations are solved in the constrained-evolution formulation under the conformally flat condition (CFC) approximation using multigrid method. % fixme: why multigrid?
In this work, for the ever first time, I have shown that cell-centred multigrid-based metric solver can not only naturally couple with finite-volume based hydrodynamics solver, but also robustly solve the highly non-linear metric equations.
Moreover, I have demonstrated that with multigrid acceleration, one can solve the metric equations on a comparable timescale as solving the hydrodynamics equations.
\texttt{Gmunu} is the first, so far the only, code that adopts multigrid metric solver in the dynamical simulations.

Gmunu 2.0
------
test test
