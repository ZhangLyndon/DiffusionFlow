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
- [**Flow and Score Matching**](labs/flow_score_matching.ipynb): Tutorials on flow matching and score matching in PyTorch. Topics include:
	- Conditional / marginal
		- Probability paths
		- Vector fields
		- Score functions
	- Gaussian conditional probability paths
		- Noise schedulers $\alpha_t$, $\beta_t$
		- Conditional flow / score matching
		- Score / vector field conversion
	- Linear conditional probability paths
	- Multilayer perceptrons (for toy data)
- [**Conditional Image Generation**](labs/conditional_image_generation.ipynb): Tutorials on conditional image generation in PyTorch. Topics include:
	- Conditional generation (guidance)
		- Class labels
		- Text prompts
	- Guided conditional flow matching
	- Classifier-free guidance
		- Guidance scale $w$
		- Marginal vector fields
			- Unguided $u_t^\text{target}(x\mid\varnothing)$
			- Guided $u_t^\text{target}(x\mid y)$
		- Classifier-free guided vector field $\tilde u_t(x\mid y)$
		- Label dropout probability $\eta$
	- Model architecture (U-Net)
		- Embeddings
			- Time step: learned sinusoidal (Fourier) frequencies
			- Class label: bias-free linear transformation
			- Projection onto channel dimension
		- Residual layers
			- Convolution
			- Nonlinearity: SiLU activation
			- Embedding integration: additive injection
			- Residual connection
				- Short range: internal to layer
				- Gradient stabilization
		- Implementation
			- Initial convolution: low-level feature map
			- Encoders
				- Residual block
				- Downsampling convolution
			- Midcoder
				- Residual block
				- Maximum channel depth
				- Minimum spatial resolution
				- Hierarchically abstracted spatial features
			- Decoders
				- Residual connection
					- Long range: corresponding encoder
					- Spatial detail recovery
				- Bilinear upsampling
				- Residual block
			- Final convolution: learned velocity field $u_t^\theta(x_t\mid y)$
		- Inference: guided ODE integration of $\tilde u_t^\theta$