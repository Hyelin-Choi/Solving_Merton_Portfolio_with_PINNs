# KIAS CAC 2024 Summer School
With Jaehoon Yoo

## 🌟 Solving Merton's Portfolio Problem: A PINN Approach 🌟

This repository contains the presentation materials and results from a project presented at the **KIAS CAC 2024 Summer School**.

The core objective of this work was to solve **Merton's Portfolio Problem** by utilizing a **Physics-Informed Neural Network (PINN)** approach. [cite_start]We also compared the solution with the exact solution[cite: 5, 6].

---

### 📝 Project Overview

[cite_start]Merton's Portfolio Problem is an optimization problem where the goal is to maximize the lifetime-aggregated utility of consumption by selecting the optimal asset allocation and consumption over time[cite: 36].

#### **Goal**
[cite_start]The primary goal was to solve the Optimal Portfolio Value Function Partial Differential Equation (PDE) using PINNs and compare the result with the known exact solution[cite: 5, 6].

#### **Merton's PDE (Optimal Value Function PDE)**
[cite_start]The Optimal Value Function, $V^{*}(t,W_{t})$, satisfies the following PDE:
$$\frac{\partial V^{*}}{\partial t}-\frac{(\mu-r)^{2}}{2\sigma^{2}}\cdot\frac{(\frac{\partial V^{*}}{\partial W_{t}})^{2}}{\frac{\partial^{2}V_{t}^{*}}{\partial W_{t}^{*}}}+\frac{\partial V^{*}}{\partial W_{t}}\cdot r\cdot W_{t}+\frac{\gamma}{1-\gamma}\cdot(\frac{\partial V^{*}}{\partial W_{t}})^{\frac{\gamma-1}{\gamma}}=\rho V^{*}.$$
The terminal condition is $V^{*}(T,W_{T})=\epsilon^{\gamma}\cdot\frac{W_{T}^{1-\gamma}}{1-\gamma}$[cite: 51].

#### **Key Constants Used**
* [cite_start]$\mu = 0.07$ (expected return on stock) [cite: 58]
* [cite_start]$r = 0.01$ (risk-free rate) [cite: 58]
* [cite_start]$\sigma = 0.2$ (volatility) [cite: 58]
* [cite_start]$T = 1$ (maturity) [cite: 58]
* [cite_start]$\gamma = 0.3$ (relative risk-aversion) [cite: 58]
* [cite_start]$\rho = 0.02$ (utility discount rate) [cite: 58]
* [cite_start]$L = 2.0$ (maximum wealth) [cite: 58]

#### **PINN Structure and Training**
* [cite_start]**Domain:** $[t_{i}, x_{j}]\in [0, T] \times [0, L]$[cite: 61].
* [cite_start]**Network Architecture:** 4 hidden layers, each with 200 perceptrons[cite: 65].
* [cite_start]**Activation Function:** Sigmoid[cite: 65].
* [cite_start]**Optimizer:** Adam with a learning rate of $1\mathrm{e}{-3}$[cite: 67].
* [cite_start]**Loss Function:** Sum of MSE losses for the initial condition, boundary condition, and the given equation (PDE)[cite: 67].
* [cite_start]**Epochs:** Trained for 10,000 epochs[cite: 66].

---

### ✨ Main Results: Solution Comparison

[cite_start]The results below illustrate the comparison between the analytically derived **Exact Solution** and the **PINN Solution**, along with the **Absolute Error** between the two (from Slide 16)[cite: 71].

| Exact Solution | PINN Solution | Absolute Error |
| :---: | :---: | :---: |
| ![Exact Solution, PINN Solution, and Absolute Error](image_9fa9fd.png) | ![Exact Solution, PINN Solution, and Absolute Error](image_9fa9fd.png) | ![Exact Solution, PINN Solution, and Absolute Error](image_9fa9fd.png) |

* [cite_start]**Image Caption:** Comparison of the Exact Solution, the PINN Solution, and the Absolute Error for the Optimal Value Function $V^{*}(t, W_t)$[cite: 71].

---

### 🤝 Collaboration

[cite_start]This work was presented by Hyelin Choi and Jung Hun Phee, and was conducted **With Jaehoon Yoo** (Sungkyunkwan University)[cite: 3].
