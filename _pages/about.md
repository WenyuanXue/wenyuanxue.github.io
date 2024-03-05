---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a first-year CEE Ph.D. student at Stanford University. My interest lies in the complex physics of nature, including fluid mechanics, solid mechanics, and fluid-solid interactions, as well as applying numerical methods to model, predict, and understand their fundamental mechanisms. Currently, I am advised by Prof. [Oliver Fringer](https://web.stanford.edu/~fringer/) and collaborating with Prof. [Yinuo Yao](https://yao-mp-lab.github.io/).

# Biography
For more detailed information, please consult my  [CV](../files/CV.pdf).


# Research

## Particle-resolved Simulation of Particle-laden Flows
Direct numerical simulation (DNS) of particle-laden flows is a powerful tool for understanding and visualizing particle-fluid and particle-particle interactions. We conducted numerical studies using an in-house particle-resolved simulation (PRS) solver ([Yao et al. 2022](https://onlinelibrary.wiley.com/doi/abs/10.1002/fld.5128)), which employs the immersed boundary method to couple Eulerian and Lagrangian fields and incorporates physical-based collision models for the particle collisions. Using this solver, several cases of fluid-particle interactions were studied and presented below.

### Sedimentation of uniformly distributed particles
Sedimentation is the process by which suspended particles settle out of the fluid due to gravity or other forces acting on them. It plays an important role in in wastewater treatment and deposition of sediments in river and estuaries. 

In our numerical studies, we examine the sedimentation of a single particle in a 3D triply-periodic domain. The particle's diameter is set at $$0.16m$$ with the particle Reynolds number $$ Re_{\tau} \approx 1.6$$. We investigated the influence of particle distance on its terminal velocity by considering domain sizes of $$ 2.56\times 2.56\times 0.64m$$, $$ 2.56\times 2.56\times 1.28m$$ and $$ 1.28\times 1.28\times 1.28m$$. The grid size is uniformly $$0.02m$$ in all directions. Using the PRS, we plotted the contour of vorticity and compared the time histories of velocity with the analytical value predicted by the Stokes' Law. The analysis shows that reducing the vertical distance increases the terminal velocity, as the drag is reduced when particles are closely aligned vertically. Conversely, reducing the horizontal distance decreases the terminal velocity, as the flow between the particles is accelerated.

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 250px; text-align: center;">
    <img src="/images/nu0.1_X2.56_Z2.56.gif" width="250px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%; margin-top: 10px; margin-bottom: 20px;">Sedimentation on grid \(2.56\times 2.56\times 2.56m\)</figcaption>
  </figure>
</div>


<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 400px; text-align: center;">
    <img src="/images/stokes.png" width="400px">
    <figcaption style="font-size: 0.8em; text-align: center; width: 100%;; margin-bottom: 0px;">Influence of distances between particles </figcaption>
  </figure>
</div>


### The drafting, kissing and tumbling process of two particles
The drafting, kissing and tumbling (DKT) process describes the dynamics and interactions between two particles moving in a fluid medium. Initially, the trailing particle accelerates as it enters the wake of the leading particle. Once the trailing particle catches up, it may collide with the leading particle and finally move away from it. The DKT process is influenced by the geometry of the system, the properties of the fluid, and the elastic and collision behaviors of particles. 

We used the PRS to investigate the influence of the initial positions of particles and their densities. Simulations were performed in a 2D domain of $$2 \times 6m$$, and the diameter of the particles was $$0.25m$$. The grid was set to $$512 \times 1536$$. The contour plots of vorticity along with the particles during the DKT process are plotted below. In the reference case (a), both particles have a density of $$\rho_p = 1500kg/m^3 $$ with an initial lateral distance of $$0.005m$$. For case (b), the density of the leading particle is changed to $$\rho_p = 1400kg/m^3$$. It is observed that the two particles do not separate before hitting the ground. For case(c), we increase the initial lateral distance to $$0.25m$$. Remarkably, the trailing particle was still drawn into the wake of the leading particle and collided with it.
<div align="center" style="display: flex; align-items: start; justify-content: center;">
  <figure style="margin-right: 30px; width: 150px; text-align: center;">
    <img src="/images/d0.005_rho2_1.5.gif" width="200">
    <figcaption style="font-size: 0.8em">(a) Reference case</figcaption>
  </figure>
  <figure style="margin-right: 30px; width: 150px; text-align: center;">
    <img src="/images/d0.005_rho2_1.4.gif" width="200">
    <figcaption style="font-size: 0.8em">(b) Leading particle lighter</figcaption>
  </figure>
  <figure style="width: 150px; text-align: center;">
    <img src="/images/d0.25_rho2_1.5.gif" width="200">
    <figcaption style="font-size: 0.8em">(c) Larger horizontal distance</figcaption>
  </figure>
</div>


### Sediment transport
Sediment transport refers to the movement of sediment particles by water across the Earth's surface. This fundamental geophysical process plays a crucial role in shaping landscapes, as well as in the formation of river channels and estuaries. Particle-resolved solvers provide us a detailed understanding of the sediment transport process, by directly modeling the fluid-particle interaction and particle-particle collision.

We utilized the PRS to investigate the movement of a particle along coarse riverbed. The 2D computation domain was set as $$2.5 \times 1.25m$$ with a grid resolution of $$ 512 \times 256 $$ and it is periodic in $$x$$-direction. The riverbed was modeled with uniform, fixed particles. We imposed a free-slip boundary condition at the top. The diameter of the particles was $$0.25m$$. Three cases of particle density were considered: $$\rho_p = 1100, 1200, 1300kg/m^3 $$. Initially, the fluid was static, then a particle was released and a constant pressure gradient of $$ \frac{\partial p}{\partial  x} = -1000 Pa/m$$ was applied. The contour plot of $$x$$-velocity along with the particles are plotted below. 

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 500px; text-align: center;">
    <img src="/images/st_rho1.1_f1000.gif" width="500px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%; margin-top: 10px; margin-bottom: 20px;">$$\rho_p = 1100kg/m^3 $$</figcaption>
  </figure>
</div>

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 500px; text-align: center;">
    <img src="/images/st_rho1.2_f1000.gif" width="500px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%; margin-top: 10px; margin-bottom: 20px;">$$\rho_p = 1200kg/m^3 $$</figcaption>
  </figure>
</div>

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 500px; text-align: center;">
    <img src="/images/st_rho1.3_f1000.gif" width="500px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%; margin-top: 10px; margin-bottom: 20px;">$$\rho_p = 1300kg/m^3 $$</figcaption>
  </figure>
</div>

# Coursework
## Fluid mechanics
ME 351A: Fluid Mechanics\\
ME 351B: Fluid Mechanics\\
CEE 262B: Transport and Mixing in Surface Water Flows\\
ENERGY 221: Fundamentals of Multiphase Flow

## Solid mechanics
CEE 310: Computational Solid Mechanics\\
CEE 314: Computational Poromechanics \\
CEE 315: Plasticity Modeling and Computation

## Numerical methods
CME 206: Introduction to Numerical Methods for Engineering\\
CME 302: Numerical Linear Algebra\\
CME 303: Partial Differential Equations of Applied Mathematics\\
CME 322: Spectral Methods in Computational Physics\\
AA 214: Numerical Methods for Compressible Flows 

