<p align="center">
  <img src="https://raw.githubusercontent.com/georgi901/numerical-heat-diffusion/main/image.png" alt="Heat Diffusion Image" width="400"/>
</p>

<h1 align="center">Solving the Heat Diffusion Equation with Python 🐍🔥</h1>

## ⇰ Description 
  This project implements and analyzes numerical methods for solving the heat diffusion (Poisson) equation using the finite difference method (FDM). The goal is to model the temperature distribution in a conductive medium under a variety of boundary conditions and conductivity models.
  The project contains implementations and experiments for:

      📎 1D model with constant conductivity — solved using the Thomas algorithm for tridiagonal systems.

      📎 1D model with variable conductivity — modified finite-difference stencil to account for k(x).

      📎 2D model on a square domain with Dirichlet boundary conditions — standard 5-point stencil.

      📎 2D model on an irregular (L-shaped) domain — masked grid formulation and solution via sparse direct methods (e.g., QR or sparse LU).

      
