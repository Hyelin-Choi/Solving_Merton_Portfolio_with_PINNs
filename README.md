# KIAS CAC 2024 Summer School
With Jaehoon Yoo

## Solving Merton's Portfolio Problem: A PINN Approach

This repository contains the presentation materials and results from a project presented at the **KIAS CAC 2024 Summer School**.

The core objective of this work was to solve **Merton's Portfolio Problem** by utilizing a **Physics-Informed Neural Network (PINN)** approach. We then compared this PINN solution with the known exact solution.

---

### Project Overview

Merton's Portfolio Problem is an optimization problem in finance. The goal is to maximize the lifetime-aggregated utility of consumption by selecting the optimal allocation and consumption at each time point.

#### Goal
The primary goal was to solve the Optimal Portfolio Value Function Partial Differential Equation (PDE) using PINNs and compare the result with the exact solution.

#### Merton's PDE (Optimal Value Function PDE)
The Optimal Value Function, $`V^{*}(t,W_{t})`$, satisfies the following PDE:
$`\frac{\partial V^{*}}{\partial t}-\frac{(\mu-r)^{2}}{2\sigma^{2}}\cdot\frac{(\frac{\partial V^{*}}{\partial W_{t}})^{2}}{\frac{\partial^{2}V_{t}^{*}}{\partial W_{t}^{*}}}+\frac{\partial V^{*}}{\partial W_{t}}\cdot r\cdot W_{t}+\frac{\gamma}{1-\gamma}\cdot(\frac{\partial V^{*}}{\partial W_{t}})^{\frac{\gamma-1}{\gamma}}=\rho V^{*}.`$

The terminal condition is $`V^{*}(T,W_{T})=\epsilon^{\gamma}\cdot\frac{W_{T}^{1-\gamma}}{1-\gamma}`$.

#### Key Constants Used
* $\mu = 0.07$ (drift / expected return on stock)
* $r = 0.01$ (risk-free rate)
* $\sigma = 0.2$ (volatility)
* $T = 1$ (maturity)
* $\gamma = 0.3$ (relative risk-aversion)
* $\rho = 0.02$ (utility discount rate)
* $L = 2.0$ (maximum wealth)

#### PINN Structure and Training
* **Domain:** The spatial domain was truncated to $[0, T] \times [0, L]$.
* **Network Architecture:** 4 hidden layers, each with 200 perceptrons.
* **Activation Function:** Sigmoid.
* **Optimizer:** Adam with a learning rate $1\mathrm{e}{-3}$.
* **Loss Function:** Sum of MSE losses of initial condition, boundary condition, and the governing PDE.
* **Epochs:** Trained for 10,000 epochs.

---

### Main Results: Solution Comparison

The 3D surface plots below compare the analytical **Exact Solution** and the **PINN Solution**, highlighting the **Absolute Error** between the two.

<img src="https://github.com/Hyelin-Choi/Solving_Merton_Portfolio_with_PINNs/blob/main/3d_plots.png">

* **Image Caption:** Comparison of the Exact Solution, the PINN Solution, and the Absolute Error for the Optimal Value Function $V^{*}(t, W_t)$.

---

### Collaboration

This work was conducted **With Jaehoon Yoo** (Sungkyunkwan University).
