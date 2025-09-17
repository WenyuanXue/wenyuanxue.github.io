---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


I am a first-year CEE Ph.D. student at Stanford University. My research interests lie in the complex physics of nature, including fluid mechanics, solid mechanics, and fluid-solid interactions, as well as applying numerical methods to model, predict, and understand their fundamental mechanisms. Currently, I am advised by Prof. [Oliver Fringer](https://web.stanford.edu/~fringer/) and collaborating with Prof. [Yinuo Yao](https://yao-mp-lab.github.io/).

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 300px; text-align: center;">
    <img src="/images/Particle_laden_flow/d0.002_rho1_2.5_rot.gif" width="300px">
  </figure>
</div>

# Biography
For more detailed information, please consult my  [CV](../files/CV.pdf).

# Research

## Particle-resolved Simulation of Particle-laden Flows
Direct numerical simulation (DNS) of particle-laden flows is a powerful tool for understanding and visualizing particle-fluid and particle-particle interactions. We conducted numerical studies using an in-house particle-resolved simulation (PRS) solver ([Yao et al. 2022](https://onlinelibrary.wiley.com/doi/abs/10.1002/fld.5128)), which employs the immersed boundary method to couple Eulerian and Lagrangian fields and incorporates physical-based collision models for the particle collisions. Using this solver, several cases of fluid-particle interactions were studied and presented below.

### Sedimentation of uniformly distributed particles
Sedimentation is the process by which suspended particles settle out of the fluid due to gravity or other forces acting on them. It plays an important role in in wastewater treatment and deposition of sediments in river and estuaries. 

In our numerical studies, we examine the sedimentation of a single particle in a 3D triply-periodic domain. We investigated the influence of particle distance on its terminal velocity by considering domain sizes of $$ 16 d_p\times 16 d_p\times 4 d_p$$, $$ 16 d_p\times 16 d_p\times 8 d_p$$ and $$ 8 d_p\times 8 d_p\times 8 d_p $$, where $$d_p$$ is the particle's diameter. The grid size is uniformly $$1/8 d_p $$ in all directions. The particle Reynolds number $$ Re_{p} \approx 1.6$$. Using the PRS, we plotted the contour of vorticity and compared the time histories of velocity with the analytical value predicted by the Stokes' Law. The analysis shows that reducing the vertical distance increases the terminal velocity, as the drag is reduced when particles are closely aligned vertically. Conversely, reducing the horizontal distance decreases the terminal velocity, as the flow between the particles is accelerated.

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 250px; text-align: center;">
    <img src="/images/Particle_laden_flow/nu0.1_X2.56_Z2.56.gif" width="250px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%; margin-top: 10px; margin-bottom: 20px;">Sedimentation on grid \(16 d_p\times 16 d_p\times 16 d_p\)</figcaption>
  </figure>
</div>


<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 400px; text-align: center;">
    <img src="/images/Particle_laden_flow/stokes.png" width="400px">
    <figcaption style="font-size: 0.8em; text-align: center; width: 100%;; margin-bottom: 0px;">Influence of distances between particles </figcaption>
  </figure>
</div>


### The drafting, kissing and tumbling process of two particles
The drafting, kissing and tumbling (DKT) process describes the dynamics and interactions between two particles moving in a fluid medium. Initially, the trailing particle accelerates as it enters the wake of the leading particle. Once the trailing particle catches up, it may collide with the leading particle and finally move away from it. The DKT process is influenced by the geometry of the system, the properties of the fluid, and the elastic and collision behaviors of particles. 

We used the PRS to investigate the influence of the initial positions of particles and their densities. Simulations were performed in a 2D domain of $$ 8 d_p \times 24 d_p$$, where $$d_p$$ is the particle's diameter. The grid was set to $$512 \times 1536$$. The contour plots of vorticity along with the particles during the DKT process are plotted below. In the reference case (a), both particles have a density of $$\rho_p = 1.5 \rho_f $$ with an initial lateral distance of $$0.02 d_p$$. For case (b), the density of the leading particle is changed to $$\rho_p = 1.4 \rho_f$$. It is observed that the two particles do not separate before hitting the ground. For case(c), we increase the initial lateral distance to $$1 d_p$$. Remarkably, the trailing particle was still drawn into the wake of the leading particle and collided with it.
<div align="center" style="display: flex; align-items: start; justify-content: center;">
  <figure style="margin-right: 30px; width: 150px; text-align: center;">
    <img src="/images/Particle_laden_flow/d0.005_rho2_1.5.gif" width="200">
    <figcaption style="font-size: 0.8em">(a) Reference case</figcaption>
  </figure>
  <figure style="margin-right: 30px; width: 150px; text-align: center;">
    <img src="/images/Particle_laden_flow/d0.005_rho2_1.4.gif" width="200">
    <figcaption style="font-size: 0.8em">(b) Leading particle lighter</figcaption>
  </figure>
  <figure style="width: 150px; text-align: center;">
    <img src="/images/Particle_laden_flow/d0.25_rho2_1.5.gif" width="200">
    <figcaption style="font-size: 0.8em">(c) Larger horizontal distance</figcaption>
  </figure>
</div>


### Sediment transport
Sediment transport refers to the movement of sediment particles by water across the Earth's surface. This fundamental geophysical process plays a crucial role in shaping landscapes, as well as in the formation of river channels and estuaries. Particle-resolved solvers provide us a detailed understanding of the sediment transport process, by directly modeling the fluid-particle interaction and particle-particle collision.

We utilized the PRS to investigate the movement of a particle along a coarse channel. The computation domain was 2D and was set as $$10 d_p \times 10d_p$$ with a grid resolution of $$ 512 \times 512 $$. It is periodic in the $$x$$-direction. The bottom of the channel was modeled with uniform, fixed particles. We also imposed a no-slip boundary condition at the top. The particle density was set at $$\rho_p = 1.5 \rho_f $$. The horizontal particle spacing was $$L = 10d_p$$. Initially, both the fluid and particles were static, then a constant pressure gradient $$ \frac{\partial p}{\partial  x} $$ was applied. Three cases of pressure gradient were considered, and the corresponding boundary Reynolds numbers $$Re_{\tau}$$, defined as $$ Re_{\tau} = \frac{u_{\tau} d_p}{\nu} = \frac{d_p}{\nu} \sqrt{-\frac{1}{\rho_f} \frac{\partial p}{\partial  x} H} $$, were equal to $$28, 35, 56$$. The $$x$$-velocity profiles and the particle movement are plotted below. 

<div align="center" style="display: flex; align-items: start; justify-content: center;">
  <figure style="margin-right: 20px; width: 200px; text-align: center;">
    <img src="/images/Particle_laden_flow/ct_rho1.5_f500.gif" width="200px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%;">$$ Re_{\tau} = 28  $$</figcaption>
  </figure>
  <figure style="margin-right: 20px; width: 200px; text-align: center;">
    <img src="/images/Particle_laden_flow/ct_rho1.5_f1000.gif" width="200px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%;">$$ Re_{\tau} = 35  $$</figcaption>
  </figure>
  <figure style=" width: 200px; text-align: center;">
    <img src="/images/Particle_laden_flow/ct_rho1.5_f2000.gif" width="200px" style="display: block; margin: auto;">
    <figcaption style="font-size: 0.75em; text-align: center; width: 100%;">$$ Re_{\tau} = 56  $$</figcaption>
  </figure>
</div>


## Phase field fracture modeling of anisotropic incompressible biological tissues

The studying and modeling of fracture behavior of soft biological tissues are critical for advancing our understanding of disease mechanisms, improving injury prevention, and enhancing surgical treatments. The challenge in accurately predicting the behavior of these tissues lies in their anisotropic and incompressible nature. 

In this study, We propose a new model for soft biological tissues that integrates the three-field mixed formulation and the phase field fracture model. The HGO model is adopted to discrible hyperelatic behavior. Anisotropy is incorporated through an anisotropic energy-based failure criterion, while the augmented Lagrangian iterations are implemented to enforce incompressibility. We demonstrate the applicability of our proposed model through the analysis of a notched strip subjected to uniaxial loading. As is shown below, the volumetric deformation remains small in the undamged region throughout the fracture process. Furthermore, we find that the augmented Lagrangian iterations has first-order convergence in certain scenarios, which aligns with the numerical results.

<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="margin: 0; width: 450px; text-align: center;">
    <img src="/images/Tissue_fracture/fracture_process.png" width="450px">
    <figcaption style="font-size: 0.8em; text-align: center; width: 100%;; margin-bottom: 0px;">Fracture process and contours of damage and volumetric deformation </figcaption>
  </figure>
</div>


<div align="center" style="justify-content: center; display: flex; flex-direction: column; align-items: center;">
  <figure style="width: 350px; text-align: center;">
    <img src="/images/Tissue_fracture/AL_cvg_numerical.png" width="350px">
    <figcaption style="font-size: 0.8em; text-align: center; width: 100%;; margin-bottom: 0px;">Convergence of augmented Lagrangian iterations </figcaption>
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

