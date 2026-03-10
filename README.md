<p align="center">
  <img src="https://raw.githubusercontent.com/georgi901/numerical-heat-diffusion/main/image.png" alt="Heat Diffusion Image" width="400"/>
</p>

<h1 align="center">Solving the Heat Diffusion Equation with Python 🐍🔥</h1>

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![Numerical Methods](https://img.shields.io/badge/Numerical-Methods-green.svg)


## ⇰ What You'll Need 

### 🧩 Required Software 
 - **Python 3.7+**
 - **Jupyter Notebook**

### 🧩 Install Dependencies 
```bash
pip install numpy matplotlib scipy jupyter
```
### 🧩 Get Started 
```bash
git clone https://github.com/georgi901/numerical-heat-diffusion.git
cd numerical-heat-diffusion
jupyter notebook
```

##  ⇰  Description 


&nbsp;&nbsp;&nbsp;&nbsp;This project implements and analyzes **numerical methods** for solving the **heat diffusion** (***Poisson***) **equation** using the **finite difference method** (***FDM***). The goal is to model the temperature distribution in a **conductive medium** under a **variety of boundary conditions** and **conductivity models**.

&nbsp;&nbsp;&nbsp;&nbsp;The project was completed as part of the ***Numerical Analysis*** course in the ***first year*** of my ***Bachelor's degree in Computer Science***.

## The Standard Mathematical Model
* &nbsp;&nbsp;&nbsp;&nbsp;The equation that describes the model:
   
  <p align="center">
  <img src="https://raw.githubusercontent.com/georgi901/numerical-heat-diffusion/main/ecuation.png" alt="Equation Image" width="400"/>
  </p>

  where $\frac{\partial u}{\partial n}(x,y)$ denotes the normal derivative of the function $u$ at the boundary. In general, one can choose:

  * The domain $\Omega$ (rectangle, $L$-shaped, circular, etc.) in $1D$ or $2D$.
  * A partition of the boundary $\partial \Omega$ into $\Gamma_D$ (Dirichlet) and $\Gamma_N$ (Neumann) parts.
  * The boundary conditions $g_D(x,y)$ and $g_N(x,y)$.
  * The thermal conductivity $k(x,y)$ (constant or space-dependent).
  * The internal heat source $f(x,y)$.

  In this project, we focus on **Dirichlet boundary conditions** with both **constant and variable conductivity**.


* &nbsp;&nbsp;&nbsp;&nbsp;The project contains implementations and experiments for:

  * **$1D$ model with constant conductivity on interval $[0, \frac{\pi}{2}]$** — solved using the ***Thomas algorithm*** for ***tridiagonal systems***.
  * **$1D$ model with variable conductivity on interval $[0,\frac{\pi}{4}]$** — ***modified finite-difference stencil*** to account for $k(x)$.
  * **$2D$ model on a square domain $[0,1] \times [0,1]$** with ***Dirichlet boundary conditions*** — standard 5-point stencil.
  * **$2D$ model on an irregular ($L$-shaped) domain** — ***masked grid formulation*** and solution via ***sparse direct solver*** (`spsolve`).
    

--- 

## ⇰ Objectives
  * ***Understand the numerical behaviour of the finite difference method.***
  * ***Test the influence of boundary conditions and thermal conductivity.***
  * ***Extend from simple*** $1D$ ***cases to more complex*** $2D$ ***geometries.***
  * ***Compare numerical solutions with available exact solutions to evaluate accuracy and convergence order.***

## ⇰ Methods and Algorithms
  * ***Uniform grid discretization*** for derivative approximations (central differences, second-order accuracy).
  * ***Thomas algorithm*** for efficiently solving the ***tridiagonal linear systems*** that appear in the $1D$ constant-coefficient case ( $O(N)$ ***complexity*** ).
  * ***Modified finite difference stencils*** to handle variable conductivity $k(x)$ in $1D$.
  * **5-point finite-difference stencil** for $2D$ ***Poisson*** problems and ***assembly of sparse linear systems***.
  * ***Sparse direct solver*** (`scipy.sparse.linalg.spsolve`) for $2D$ problems, including irregular domains where the matrix structure is not ***block-tridiagonal***.
  * ***Cubic spline interpolation*** ($1D$) and ***bicubic spline interpolation*** ($2D$) for smooth reconstruction of the numerical solution between grid nodes.

## ⇰ Results
  * Convergence study showing an **empirical order &approx; 2 for central finite differences**.
  * Plots comparing **numerical solution** vs **exact solution** ( *when available* ) and pointwise **error maps** in $1D$ and $2D$.
  * Maximum error values for several **mesh sizes** and a **log-log plot** of **error** vs **grid spacing** $h$.
  * $2D$ **contour**, **heatmap**, and **3D surface plots** for temperature distribution on the **square** and $L$**-shaped domains**.
  * **Cross-section plots** at constant $y$ comparing numerical and exact solutions in $2D$.
  * **Cubic** and **bicubic spline interpolation** of the numerical solution for smooth visualization.
    
## ⇰ Usage 
### Running Models
The notebook contains separate sections for each model mentioned above.
Simply run each cell sequentially to see the numerical solutions and error analysis.
