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
* &nbsp;&nbsp;&nbsp;&nbsp;The ecuation that respect the model :
   
  <p align="center">
  <img src="https://raw.githubusercontent.com/georgi901/numerical-heat-diffusion/main/ecuation.png" alt="Ecuation Image" width="400"/>
  </p>

  where $\frac{\partial u}{\partial n}(x,y)$ denotes the normal derivative of the function $u$ at the boundary. You will choose:

  * The $2D$ domain $\Omega$ (rectangle, $L$-shaped, circular, etc.) or $3D$.
  * A partition of the boundary $\partial \Omega$ into two parts, $\Gamma_D \subset \partial \Omega$, the portion of the boundary where the $Dirichlet$ condition is applied, and $\Gamma_N = \partial \Omega \setminus \Gamma_D$, the portion of the boundary where the $Neumann$ condition is applied.
  * The boundary conditions on this partition, $g_D(x,y)$ and $g_N(x,y)$.
  * The thermal conductivity of the material, $k(x,y)$ (constant or space-dependent).
  * The internal heat source of the material, $f(x,y)$.


* &nbsp;&nbsp;&nbsp;&nbsp;The project contains implementations and experiments for:

  * **$1D$ model with constant conductivity on interval $[0,1]$** — solved using the ***Thomas algorithm*** for ***tridiagonal systems***.
  * **$1D$ model with variable conductivity on interval $[0,\frac{\pi}{4}]$**— ***modified finite-difference stencil*** to account for $k(x)$.
  * **$2D$ model on a square domain $[0,1] \times [0,1]$ with ***Dirichlet boundary conditions*****— standard 5-point stencil.
  * **$2D$ model on an irregular ($L$-shaped) domain** — ***masked grid formulation*** and solution via sparse direct methods (e.g., ***QR*** or sparse ***LU***).
    

--- 

## ⇰ Objectives
  * ***Understand the numerical behaviour of the finite difference method.***
  * ***Test the influnce of boundary conditions and thermal conductivity.***
  * ***Extend from simple*** $1D$ ***cases to more complex*** $2D$ ***geometries.***
  * ***Compare numerical solutions with available exact solutions to evaluate accuracy and convergence order.***

## ⇰ Methods and Algorithms
  * ***Uniform grid discretization*** for derivative aproximations (central differences, second order accuracy).
  * ***Thomas algorithm*** for efficiently solving the ***tridiagonal linear systems*** that appper in the $1D$ constant-coefficient case ( $O(N)$ ***complexity*** ).
  * ***Modified finite difference stencils*** to handel variable conductivity $k(x)$ in $1D$.
  * **5-point finite-difference stencil** for $2D$ ***Poisson*** problems and ***assembly of sparse linear systems***.
  * ***Sparse direct solvers*** / ***QR factorization*** for irregular domains where the matrix structure is not ***Block-tridiagonal***.

## ⇰ Expected Results
  * Convergence study showing an **empirical order &approx; 2 for central finite differences**.
  * Plots comparing **numerical solution** vs **exact soltion** ( *when available* ) and pointwise **error maps** in $1D$ and $2D$.
  * Maximum error values for several **mesh sizes** and a **log-log plot** of **error** vs **grid spacing** $h$.
  * $2D$ **contour** and **surface plots for temperature distribution** on the **square** and $L$ **-shaped domains**.
    
## ⇰ Usage 
### Running Models
The notebook contains separate sections for each model mentionated earlyer.
Simply run each cell sequentially to see the numerical solutions and error analysis.


    
    


    

