<div align = "center">

# Flow Matching and Diffusion Models

Labs for the [Flow Matching and Diffusion Models](https://diffusion.csail.mit.edu) course.

[**About**](#about)
| [**Labs**](#labs)

</div>

## About

This repository contains labs (i.e., tutorials) produced while completing the Introduction to Flow Matching and Diffusion Models course (6.S184/6.S975) from [MIT EECS](https://www.eecs.mit.edu).

## Labs

The following labs were completed while working on the course.

- [**Stochastic Differential Equations**](labs/sde.ipynb): Tutorials on stochastic differential equations (SDEs) in PyTorch. Topics include:
	- Drift $\mu_t(X_t)$ and diffusion $\sigma_t$ coefficients
	- Numerical methods
		- Euler method (ODE)
		- Euler-Maruyama method (SDE)
	- Classes of SDEs
		- Brownian motion
		- Ornstein-Uhlenbeck processes
		- Overdamped Langevin dynamics
	- Score function $\nabla\log p_t(x)$