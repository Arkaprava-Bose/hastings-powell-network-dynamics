# Synchronization and Spatiotemporal Dynamics in Networks of Chaotic Hastings–Powell Oscillators

## Overview

The Hastings–Powell model is a simple three-species predator–prey system capable of exhibiting chaotic behaviour biogolically realizeable parameter regimes [1] . We study a system where such patches are allowed to communicate via diffusion. In such a system, competition between divergent local dynamics and convergent diffusive convergence governs the network dynamics. Therefore exhibiting **Chaos Synchronization**.

Finally, in the work of Janaki et al. [5], we analyse spatio-temporal patterns in Rozenwig-McArthur wich atmost shows oscillatory behaviour in . We consider the Hastings-Powell as the natural extension of this where interest ourselves in exploring spatio-temporal patterns in chaotic regime of an isolated patch.


Current work:

- Chaotic dynamics of the isolated oscillator
- Synchronization in one-dimensional chains
- Synchronization in two-dimensional lattices

Currently under investigation:

- Spatiotemporal pattern formation
- Pattern Classification

---

## Mathematical Model

For an isolated oscillator, the Hastings-Powell model considers a three-trophic food chain where x, y and z represent basal resource (vegetation) , consumer (herbivore) and top predator (carnivore).Basal resource is considered to have logistic growth and predation by consumer, consumers grow by predation over basal population and exhibits exponential natural death and predation by top predators. Top-predators grow via predation on consumers and exhibits exponential natural death.  The response of predation is modeled by Holling Type II functional response. Consumer and top predators are considered to be more mobile than basal resource.
Therefore spacial coupling is introduced only through consumers and predators.

$$
\frac{dX_i}{dT} =
R_0X_i\left(1-\frac{X_i}{K_0}\right) -
C_1F_1(X_i)Y_i,
$$

$$
\frac{dY_i}{dT} =
F_1(X_i)Y_i -
F_2(Y_i)Z_i -
D_1Y_i +
\frac{D_Y}{k_i}\sum_{j=1}^{N}G_{ij}Y_j,
$$

$$
\frac{dZ_i}{dT} =
C_2F_2(Y_i)Z_i -
D_2Z_i +
\frac{D_Z}{k_i}\sum_{j=1}^{N}G_{ij}Z_j,
$$

where the Holling Type II functional responses are

$$
F_i(U) =
\frac{A_iU}{B_i+U},
\qquad i=1,2.
$$

where $G$ is the graph Laplacian, $k_i$ is the degree of node $i$, and $D_y$ and $D_z$ are the diffusion coefficients.

The current implementation considers the following network topologies and coupling schemes:

- **One-dimensional chain** with nearest-neighbor diffusive coupling.
- **Two-dimensional square lattice** with nearest-neighbor diffusive coupling.
- **Open (absorbing)** and **periodic (toroidal)** boundary conditions.
- **Degree-normalized graph Laplacian** coupling, ensuring a uniform effective coupling strength across nodes with different degrees.
---

## Repository Structure

```
src/
    Core MATLAB functions

examples/
    Scripts reproducing the main simulations

figures/
    Generated figures

animations/
    Movies of synchronization and lattice evolution

docs/
    Theory, equations and numerical methods

results/
    Simulation outputs
```

---

## Numerical Methods

The simulations and analyses in this repository employ the following numerical and computational techniques:

- Numerical integration using MATLAB ODE solver (`ode45`)
- Graph Laplacian-based degree-normalized diffusive coupling on network topologies
- Poincaré section-based phase extraction
- Pairwise phase synchronization analysis
- Power spectral density (PSD) estimation using Welch's method
- Jensen–Shannon divergence (JSD) for quantitative comparison of spectral distributions
- Pairwise frequency synchronization analysis
- Phase-space, spectral, and spatiotemporal visualization tools

---

## Main Results

### 1. Isolated Hastings–Powell Dynamics

The isolated Hastings–Powell oscillator exhibits rich nonlinear dynamics, including deterministic chaos. The repository focuses on the chaotic nautre of dynamics in biologically attainable parameter regimes. Numerical simulations of the three-species food chain together with phase-space trajectories to characterize the underlying attractor.

Representative results:
- Chaotic phase portrait in $(x,y,z)$ space
- Time series of prey, predator, and top-predator populations
- Power spectral density (PSD) of the isolated oscillator

---

### 2. Synchronization in One-Dimensional Chains

The emergence of collective dynamics is investigated in one-dimensional nearest-neighbor coupled chains. Synchronization is quantified using phase-locking measures obtained from Poincaré sections together with pairwise phase differences.

Representative results:
- Examplar time series and phase-space trajectories of coupled oscillators in unsynchronized and synchronized parameter 
- Heat maps over the $(D_y,D_z)$ parameter space

---

### 3. Synchronization in Two-Dimensional Lattices

The synchronization properties of chaotic Hastings–Powell oscillators are extended to two-dimensional square lattices with nearest-neighbor coupling. Open (absorbing) are implemented using a degree-normalized graph Laplacian.

Representative results:
- Synchronization phase diagrams in diffusion parameter space
- Power spectral density comparison across lattice nodes
- Heat maps based on pairwise synchronization measures

---

## References

1. Hastings & Powell (1991) — Chaos in a Three-Species Food Chain.
2. A. Pikovsky, M. Rosenblum, and J. Kurths (2001) — Synchronization: A Universal Concept in Nonlinear Sciences.
3. S. H. Strogatz (2015) — Nonlinear Dynamics and Chaos (2nd ed.).
4. L. M. Pecora and T. L. Carroll (1990) — Synchronization in Chaotic Systems.
5. R. Janaki, S. N. Menon, R. Singh, and S. Sinha (2021) — Lateral inhibition provides a unifying framework for spatiotemporal pattern formation in media comprising relaxation oscillators.
---

## Author

Arkaprava Bose

Integrated BS–MS, IISER Kolkata

Summer Intern at IMSc, Chennai

Supervisor: Sitabhra Sinha
