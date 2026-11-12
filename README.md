# encs4380-dynamics-group-3
Interactive toolkit for exploring the dynamic characteristics of sensors using simulations and real-time plots.

# ENCS4380 — Dynamic Characteristics Interactive Toolkit

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-brightgreen?logo=github)](https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/)
[![Course](https://img.shields.io/badge/Birzeit%20University-ENCS4380%20Interfacing%20Techniques-blue)](https://www.birzeit.edu/)
[![Release](https://img.shields.io/badge/Release-v1.0-orange)](https://github.com/mayarmualla6-hub/encs4380-dynamics-group-3/releases/tag/v1.0)
[![Validation](https://img.shields.io/badge/Validation%20Tests-6%2F6%20Passing-success)](#-system-validation-results-66-passed)

> An interactive web-based simulation toolkit built for **ENCS4380: Interfacing Techniques** at Birzeit University. This toolkit models, simulates, and analyzes the dynamic response characteristics of first-order and second-order sensors in both time and frequency domains.

---

## 🌐 Live Interactive Application
👉 **Access the Live Toolkit on GitHub Pages:**  
**[https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/?fbclid=IwZXh0bgNhZW0CMTEAcGRvZgNzcnRjBmFwcF9pZA80Mzc2MjYzMTY5NzM3ODgAAR_SF8uE-GI4RTKmSXyKaLxiNRW7nmNT2wf0dpnTr9arl6lCh25yvgKXJDRHnw_aem_tg2Aiut4KWEOCk97Y89S4g#module4)**  
*(Optimized for both desktop and mobile phone browsers with responsive controls)*

---

## 👥 Group 3 (HLMA) — Team Members & Ownership

| Team Member Name | Student ID | Assigned Module | Key Responsibilities & Contributions |
| :--- | :---: | :---: | :--- |
| **Amal Khalifah** | `1230313` | **Module 1** | First-order step/ramp models, $\tau$ & $3\tau$ markers, log-error regression plot ($\ln E$ slope $-1/\tau$), quiz logic. |
| **Mayar Mualla** | `1230690` | **Module 2** | Frequency response, sine input/output visualizer, Bode magnitude/phase plots, dynamic error calculator ($\delta = M - 1$). |
| **Hala Elayyan** | `1230150` | **Module 3** | Second-order response, Runge-Kutta (RK4) simulator (`simulate3`), state-space matrix formulation ($A, B$), eigenvalue calculation. |
| **Laila Awad** | `1230085` | **Module 4 & Bonus** | "Guess the Sensor" reverse-engineering game engine, noise injection, multi-trace overlays, phase plane ($(x_1, x_2)$ spiral), 6/6 validation tests, and bonus implementation. |

*Each member's assigned ownership corresponds directly to dedicated GitHub Issues and commit logs.*

---

## 📸 Screenshots

### Module 1: First-Order Time Response & Error Fraction
![Module 1 Screenshot](C:\Users\Lenovo\Pictures\Screenshots\M1.png)
![Module 1 Screenshot](C:\Users\Lenovo\Pictures\Screenshots\M2.png)
![Module 1 Screenshot](C:\Users\Lenovo\Pictures\Screenshots\M3.png)

### Module 2: Frequency Response & Bode Plot Analysis
![Module 2 Screenshot](images/module2.png)

### Module 3: Second-Order Response & State-Space Phase Plane
<img width="842" height="405" alt="image" src="https://github.com/user-attachments/assets/209aa3bf-4c70-4798-b6ed-423cfaff2cd9" />
<img width="849" height="369" alt="image" src="https://github.com/user-attachments/assets/40ededc5-b23d-4a74-966f-fc1dd4bf99d5" />
<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/2af9f973-3827-4197-ae8f-98a2a114b7d7" />
<img width="467" height="423" alt="image" src="https://github.com/user-attachments/assets/7b407602-f222-476b-a5dd-d83d0a290ffe" />
<img width="900" height="194" alt="image" src="https://github.com/user-attachments/assets/5aa29ced-0f0d-4271-a60d-50fc9d97d2af" />



### Module 4: "Guess the Sensor" Reverse-Engineering Challenge
<img width="1003" height="522" alt="image" src="https://github.com/user-attachments/assets/73ad2eaa-c5f7-4415-99e9-00498c7222b6" />

### Bonus Module: Superposition Harmonic Distortion & ODE Solver Benchmarking
<img width="1096" height="804" alt="image" src="https://github.com/user-attachments/assets/caa3ca8f-0206-455d-b5da-e31ee01aac11" />

---

## 🚀 Key Modules Overview

### 1. Module 1: First-Order Time Response (Thermometer Model)
* **Governing Equation:** $\tau \dot{y} + y = K x \implies G(s) = \frac{K}{\tau s + 1}$
* **Step Response:** $y(t) = K A (1 - e^{-t/\tau})$ with dynamic markers for $t = \tau$ ($63.2\%$) and $t = 3\tau$ ($95.0\%$).
* **Ramp Response:** Shows steady-state time lag $e_{ss} = \tau$ and steady-state error $K A \tau$.
* **Logarithmic Error Plot:** Evaluates error fraction $E(t) = e^{-t/\tau}$ on a logarithmic scale; confirms the linear slope equals $-\frac{1}{\tau}$ via live least-squares fit.
* **Interactive Feature:** "Predict, then check" active conceptual quiz.

### 2. Module 2: First-Order Frequency Response
* **Governing Equation:** $M(\omega) = \frac{1}{\sqrt{1 + (\omega\tau)^2}}$, $\phi(\omega) = -\tan^{-1}(\omega\tau)$
* **Visualizer:** Side-by-side time-domain input/output sines demonstrating amplitude attenuation and time delay $\Delta t = \frac{|\phi|}{\omega}$.
* **Bode Plots:** Magnitude (dB) and Phase (degrees) plotted on a logarithmic frequency axis with cutoff frequency $\omega_c = \frac{1}{\tau}$ ($-3\text{ dB}$, $-45^\circ$).
* **Dynamic Error Calculator:** Calculates maximum allowable time constant:
  $$\tau_{\max} = \frac{\sqrt{\frac{1}{(1-\varepsilon)^2} - 1}}{2\pi f}$$

### 3. Module 3: Second-Order Response & State-Space Representation
* **Governing Equation:** $m\ddot{x} + b\dot{x} + kx = F(t)$, with $\omega_n = \sqrt{\frac{k}{m}}$ and $\zeta = \frac{b}{2\sqrt{km}}$
* **Numerical Simulation:** Implements a 4th-Order Runge-Kutta (RK4) integrator (`simulate3`) from course notes (Section 7.1).
* **Dynamic Metrics:** Live extraction of Rise Time ($10\%\to90\%$), Peak Time ($t_p$), Percent Overshoot ($\%OS$), and Settling Time ($\pm 2\%$).
* **State-Space Panel:**
  $$\dot{\mathbf{x}} = \begin{bmatrix} 0 & 1 \\ -\frac{k}{m} & -\frac{b}{m} \end{bmatrix} \mathbf{x} + \begin{bmatrix} 0 \\ \frac{1}{m} \end{bmatrix} F, \quad y = \begin{bmatrix} 1 & 0 \end{bmatrix} \mathbf{x}$$
* **Eigenvalues vs. Poles:** Proves that the eigenvalues of state matrix $A$ directly match the poles in the complex $s$-plane.
* **Phase Plane:** Plots velocity ($\dot{x}$) vs. position ($x$), visually displaying the spiral convergence for underdamped systems versus direct non-spiraling convergence for overdamped/critically damped systems.

### 4. Module 4: "Guess the Sensor" Reverse-Engineering Challenge
* **Challenge Engine:** Randomly instantiates a hidden 1st-order sensor $(K, \tau)$ or 2nd-order sensor $(\zeta, \omega_n)$ with Gaussian measurement noise.
* **Input Scenarios:** Supports step inputs as well as sinusoidal inputs at given frequencies.
* **Estimation Methodology:** 
  * For 1st-order step: identify final value $K$ and time to $63.2\%$ for $\tau$.
  * For 1st-order sine: extract amplitude attenuation $M$ to compute $\tau = \frac{\sqrt{(1/M)^2 - 1}}{\omega}$.
  * For 2nd-order: inspect peak overshoot for $\zeta$ ($\%OS = 100 e^{-\pi\zeta/\sqrt{1-\zeta^2}}$) and peak time for $\omega_n$.
* **Visual Scoring & Reveal:** Overlays the noisy sensor reading against the user's estimated curve and the true clean sensor model. Awards full marks ($100\text{ pts}$) for estimates within $\le 10\%$ error.

---

## 🌟 Bonus Module: Superposition & Numerical ODE Solver

As specified in **Section 8 (Bonus Points)** of the project guidelines, our team implemented:

1. **Multi-Sine Superposition & Harmonic Distortion Explorer:**
   * Generates a multi-frequency input:
     $$x(t) = A_1 \sin(2\pi f_1 t) + A_2 \sin(2\pi (3f_1) t) + A_3 \sin(2\pi (5f_1) t)$$
   * Demonstrates how a first-order sensor acts as a low-pass filter, phase-lagging and attenuating higher harmonics more severely than the fundamental, resulting in severe output waveform shape distortion.
2. **Numerical ODE Solver Comparison (Analytical vs. Forward Euler vs. RK4):**
   * Solves the sensor differential equation $\tau \dot{y} + y = u(t)$ numerically in real-time.
   * Compares the closed-form exact solution against Forward Euler and 4th-Order Runge-Kutta (RK4).
   * **Stability Analysis:** Graphically displays the Forward Euler stability limit ($h < 2\tau$). When the user increases the step size $h \ge 2\tau$, the simulation clearly illustrates numerical oscillation and divergence.

---

## 🧪 System Validation Results (6/6 Passed)

The application includes live programmatic checks directly implementing the lecture slide test cases:

| # | Validation Criteria | Expected Reference | Toolkit Output | Status |
| :-: | :--- | :---: | :---: | :-: |
| **1a** | First-order step response at $t = \tau$ | $y(\tau) = 0.632 KA$ | `0.632` | <kbd>✓ PASS</kbd> |
| **1b** | First-order step response at $t = 3\tau$ | $y(3\tau) = 0.950 KA$ | `0.950` | <kbd>✓ PASS</kbd> |
| **2a** | $\tau = 0.2\text{ s}$, input $\sin(2t)$: Amplitude ratio $M$ | $M = 0.93$ | `0.928` | <kbd>✓ PASS</kbd> |
| **2b** | $\tau = 0.2\text{ s}$, input $\sin(2t)$: Phase lag $\phi$ | $\text{Lag} = 21.8^\circ$ | `21.80°` | <kbd>✓ PASS</kbd> |
| **3a** | Signals up to $100\text{ Hz}$ with $\le 5\%$ error: $\tau_{\max}$ | $\tau_{\max} \approx 0.52\text{ ms}$ | `0.523 ms` | <kbd>✓ PASS</kbd> |
| **3b** | Phase lag at $50\text{ Hz}$ with $\tau_{\max}$ | $\text{Lag} = 9.3^\circ$ | `9.34°` | <kbd>✓ PASS</kbd> |
| **4** | Second-order overshoot with $\zeta = 0.5$ | $\%OS = 16.3\%$ | `16.30%` | <kbd>✓ PASS</kbd> |
| **5** | Second-order overshoot with $\zeta = 1.0$ (Critical) | $\%OS = 0.0\%$ | `0.00%` | <kbd>✓ PASS</kbd> |
| **6** | State Space ($m=1, b=2, k=4$): Eigenvalues of $A$ | $\lambda = -1 \pm j1.732$ | `-1.000 ± j1.732` | <kbd>✓ PASS</kbd> |

---

## 📂 Repository Structure

```text
encs4380-dynamics-group-3/
│
├── index(1).html          # Core single-page interactive application (all modules + bonus)
├── README.md           # Documentation, team responsibilities, formulas, and screenshots
└── images/             # Verification and demonstration screenshots
    ├── module1.png
    ├── module2.png
    ├── module3.png
    ├── module4.png
    └── bonus.png
