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
**[https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/](https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/)**  
*(Optimized for both desktop and mobile phone browsers with responsive controls)*

---

## 👥 Group 3 (HLMA) — Team Members & Ownership

| Team Member Name | Student ID | Assigned Module | Key Responsibilities & Contributions |
| :--- | :---: | :---: | :--- |
| **Amal Khalifah** | `1230313` | **Module 1** | First-order step/ramp models, $\tau$ & $3\tau$ markers, log-error regression plot ($\ln E$ slope $-1/\tau$), quiz logic. |
| **Mayar Mualla** | `1230690` | **Module 2** | Frequency response, sine input/output visualizer, Bode magnitude/phase plots, dynamic error calculator ($\delta = M - 1$). |
| **Hala Elayyan** | `1230150` | **Module 3** | Second-order response, Runge-Kutta (RK4) simulator (`simulate3`), state-space matrix formulation ($A, B$), eigenvalue calculation. |
| **Laila Awad** | `1230085` | **Module 4 & Bonus** | "Guess the Sensor" game engine, Bonus implementation (Superposition & ODE solver), full `README.md` documentation, GitHub Issues setup, and `v1.0` Release deployment. |

*Each member's assigned ownership corresponds directly to dedicated GitHub Issues and commit logs.*

---

## 📸 Screenshots

### Module 1: First-Order Time Response & Error Fraction
<img width="674" height="830" alt="image" src="https://github.com/user-attachments/assets/631a778d-3f35-4b52-adcc-bd741fbf4d28" />

### Module 2: Frequency Response & Bode Plot Analysis
<img width="712" height="820" alt="image" src="https://github.com/user-attachments/assets/707ed4dd-4eaf-43e0-a66e-c1bdef8a8212" />
<img width="665" height="321" alt="image" src="https://github.com/user-attachments/assets/c163c698-ac1e-4988-bc32-f75385d3e3b0" />

### Module 3: Second-Order Response & State-Space Phase Plane
<img width="842" height="405" alt="image" src="https://github.com/user-attachments/assets/209aa3bf-4c70-4798-b6ed-423cfaff2cd9" />
<img width="849" height="369" alt="image" src="https://github.com/user-attachments/assets/40ededc5-b23d-4a74-966f-fc1dd4bf99d5" />
<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/2af9f973-3827-4197-ae8f-98a2a114b7d7" />
<img width="467" height="423" alt="image" src="https://github.com/user-attachments/assets/7b407602-f222-476b-a5dd-d83d0a290ffe" />
<img width="900" height="194" alt="image" src="https://github.com/user-attachments/assets/5aa29ced-0f0d-4271-a60d-50fc9d97d2af" />

### Module 4: "Guess the Sensor" Reverse-Engineering Challenge
<img width="1003" height="522" alt="image" src="https://github.com/user-attachments/assets/73ad2eaa-c5f7-4415-99e9-00498c7222b6" />
<img width="744" height="394" alt="image" src="https://github.com/user-attachments/assets/0aab3240-ebba-466b-94e3-8901e2b5c8c6" />

### Bonus Module: Superposition Harmonic Distortion & ODE Solver Benchmarking
<img width="1096" height="804" alt="image" src="https://github.com/user-attachments/assets/caa3ca8f-0206-455d-b5da-e31ee01aac11" />
<img width="698" height="539" alt="image" src="https://github.com/user-attachments/assets/61264d87-6e29-40d0-b1f3-753119514b1a" />

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

<!-- =====================================================================
     README additions for Homework 2 — Group 3 (HLMA)
     Four pieces, each says WHERE it goes. Fill every "TODO" before v2.0.
     ===================================================================== -->


<!-- ===================== PIECE 1 — REPLACE the 4 badge lines at the top ===================== -->

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-brightgreen?logo=github)](https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/)
[![Course](https://img.shields.io/badge/Birzeit%20University-ENCS4380%20Interfacing%20Techniques-blue)](https://www.birzeit.edu/)
[![Release](https://img.shields.io/badge/Release-v2.0-orange)](https://github.com/mayarmualla6-hub/encs4380-dynamics-group-3/releases/tag/v2.0)
[![HW1 Validation](https://img.shields.io/badge/HW1%20Validation-9%2F9%20Passing-success)](#-system-validation-results-66-passed)
[![HW2 Validation](https://img.shields.io/badge/HW2%20PID%20Validation-7%2F7%20Passing-success)](#-homework-2-validation-results-77-passed)


<!-- ===================== PIECE 2 — INSERT right after the "Live Interactive Application" section ===================== -->

## 🎛️ Homework 2: PID Control Toolkit

👉 **Control section (P1–P4):** **[control.html](https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/control.html)**  
👉 **Our own system:** **[my-system.html](https://mayarmualla6-hub.github.io/encs4380-dynamics-group-3/my-system.html)**  
*(Linked from the landing page through the **Control (HW2) →** tab.)*

Homework 1 showed how slow a sensor or plant is. Homework 2 shows how **feedback** makes it faster and more accurate. Every plot is computed live in the browser by our own closed-loop simulation, stepped in time with **4th-order Runge–Kutta (RK4)**. Nothing is precomputed and there is no server.

### 👥 Homework 2 Module Ownership

<!-- TODO: confirm who owns what, and fill in the issue numbers -->
| Team Member | Module | What it shows | GitHub Issue |
| :--- | :---: | :--- | :---: |
| **Amal Khalifah** | **P1: PID Playground** | Block diagram, P/I/D sliders, output vs setpoint, control signal and its limit, live rise / overshoot / settling / steady-state error, validation checks | #TODO |
| **Mayar Mualla** | **P2: Slow Sensor in the Loop** | First-order sensor $\tau_s$ in the feedback path; true output vs sensor reading; overshoot-vs-$\tau_s$ sweep; Routh–Hurwitz oscillation limit | #TODO |
| **Hala Elayyan** | **P3: Digital PID** | Sampled PID with zero-order hold, stair-step $u[k]$, performance vs $T_s$, anti-windup toggle, generated Arduino code with copy button | #TODO |
| **Laila Awad** | **P4: Tuning Challenge** | Random hidden plant (as in Module 4), spec with pass/fail per part and a score | #TODO |
| **All members** | **My System** | Our own plant: fitted $K$, $\tau$, chosen spec, final gains, simulated response, Arduino code | #TODO |

### 🧠 How the simulation works

* **Plants**
  * First order (Module 1): $\tau\dot{y} + y = K u \implies G(s) = \dfrac{K}{\tau s + 1}$
  * Second order (Module 3): $m\ddot{y} + b\dot{y} + k y = k\,u \implies G(s) = \dfrac{k}{m s^2 + b s + k}$
* **Continuous PID** (P1, P2, P4, My System):
  $$u = K_p e + K_i \int e\,dt - K_d \frac{dy_m}{dt}, \qquad e = r - y_m$$
  * The derivative acts on the **measurement**. For a step setpoint this equals $K_d\,\dot e$ for every $t > 0$, and it avoids the infinite "derivative kick" at $t = 0$. It is filtered with $T_f = 0.02 \times$ the plant time scale.
  * $u$ is clamped to the actuator limits, with **anti-windup by clamping**: the integrator stops while $u$ is saturated and the error would push it further into saturation.
* **Slow sensor** (P2): $\tau_s \dot{y}_m + y_m = y$. The controller only ever sees $y_m$.
* **Digital PID** (P3), exactly the formula from the handout, held constant between samples (zero-order hold):
  $$u[k] = K_p e[k] + K_i T_s \sum_{j=0}^{k} e[j] + K_d \frac{e[k]-e[k-1]}{T_s}$$
  The simulation uses the same `pidStep` logic as the generated Arduino code.
* **Solver:** fixed-step RK4 on the whole loop state $[\,y\ (\dot y)\ |\ y_m\ |\ \int e\ |\ \text{derivative filter}\,]$. The step size shrinks automatically with the gains and time constants. A response that grows past $10^4 r$ is flagged **unstable**.
* **Metrics** (same definitions as Module 3): rise time $10\% \to 90\%$, percent overshoot, settling time $\pm 2\%$, steady-state error $(r - y_\infty)/r$.

### 🔎 Module highlights

* **P1:** The **P only, Kp = 9** button cuts the closed-loop $\tau$ from $1$ s to $0.1$ s, but leaves $e_\infty = \frac{1}{1+KK_p} = 10\%$. Adding $K_i$ removes that error. On the second-order plant, $K_d = 0.3$ cuts the overshoot from about $29\%$ to about $13\%$.
* **P2:** With $K_p = 4$, $K_i = 10$ on $\frac{1}{s+1}$, Routh–Hurwitz on $\tau\tau_s s^3 + (\tau+\tau_s)s^2 + (1+KK_p)s + KK_i$ predicts sustained oscillation at $\tau_s = 1.0$ s. The live sweep shows the overshoot climbing towards it, and the loop goes unstable past it.
* **P3:** Large $T_s$ acts like a delay of about $T_s/2$; the loop above breaks down around $T_s \approx 0.4$ s. With $|u| \le 2$, switching anti-windup **off** raises the overshoot from about $2\%$ to about $28\%$.
* **P4:** The settling-time limit is set from a gain search, so every random plant is guaranteed to be tunable. Score: overshoot $\le 10\%$ (35 pts), settling time (35 pts), $|e_\infty| \le 1\%$ (30 pts).

### ⚙️ Our System: TODO (e.g. micromouse drive motor, speed loop)

<!-- TODO: replace every value below with your measured numbers -->
| Item | Value | Source |
| :--- | :---: | :--- |
| Plant model | $G(s) = \dfrac{K}{\tau s + 1}$ | First-order fit of a PWM step test |
| Gain $K$ | TODO (mm/s per % PWM) | TODO: e.g. PWM step 0 → 60 %, encoder logged at 200 Hz |
| Time constant $\tau$ | TODO s | TODO: time to 63.2 % of the final speed |
| Spec | $\zeta =$ TODO, $t_s \le$ TODO s, PWM within 0–100 % | TODO: one sentence on why this matters for the project |
| Final gains | $K_p =$ TODO, $K_i =$ TODO, $K_d = 0$ | Pole placement: $K_p = \frac{2\zeta\omega_n\tau - 1}{K}$, $K_i = \frac{\omega_n^2\tau}{K}$ |
| Arduino sampling time | $T_s =$ TODO s | ≥ 10 samples per rise time |

### 📸 Homework 2 Screenshots
<!-- TODO: under each title, drag the screenshot into GitHub's README editor; it inserts the <img> line for you. -->

#### Landing Page: Link to the Control Section
<!-- screenshot: the HW1 page header with the "Control (HW2) →" tab and the Homework 2 card -->

#### P1: PID Playground (Output vs Setpoint, Control Signal & Live Metrics)
<!-- screenshot: block diagram + output chart + control-signal chart + metric cards (e.g. after "P only, Kp = 9") -->

#### P1: Validation Checks (7/7 Passed)
<!-- screenshot: the validation table, all green -->

#### P2: Slow Sensor in the Loop (True Output vs Sensor Reading)
<!-- screenshot: τs around 0.3–0.5 s so the cyan and pink curves clearly separate -->

#### P2: The Move to Oscillation (Overshoot vs τs Sweep & Routh–Hurwitz Limit)
<!-- screenshot: the sweep chart with red points + the Routh sentence (press "Edge of oscillation") -->

#### P3: Digital PID (Stair-Step u[k] & Digital vs Continuous Output)
<!-- screenshot: Ts around 0.1–0.2 s so the steps are visible -->

#### P3: Performance vs Sampling Time & Anti-Windup
<!-- screenshot: the Ts sweep chart, and the response after "Show windup" with anti-windup OFF -->

#### P3: Generated Arduino Code
<!-- screenshot: the code panel with the Copy button -->

#### P4: Tuning Challenge (Open-Loop Test, Spec & Score)
<!-- screenshot: a round with 100/100 and all three parts ✓ PASS -->

#### My System: Plant Model, Spec & Design Checks
<!-- screenshot: model + spec + final gains + design checks table -->

#### My System: Simulated Speed Response, PWM Command & Arduino Code
<!-- screenshot: response chart + PWM chart (within 0–100 %) + code -->

#### Mobile View
<!-- screenshot: control.html on a phone -->


---

## 🧪 Homework 2 Validation Results (7/7 Passed)

Plant $\frac{K}{\tau s + 1}$ with $K = 1$, $\tau = 1$ s. The values are **measured from the RK4 simulation**, except rows 2a and 2b, which come from the closed-loop formula. They are shown live on the Control page.

| # | Validation Criteria | Expected Reference | Toolkit Output | Status |
| :-: | :--- | :---: | :---: | :-: |
| **1a** | P only, $K_p = 9$: closed-loop $\tau$ | $0.100$ s | `0.1000 s` | <kbd>✓ PASS</kbd> |
| **1b** | P only, $K_p = 9$: steady-state error $\frac{1}{1+KK_p}$ | $10\%$ | `10.000%` | <kbd>✓ PASS</kbd> |
| **2a** | PI, $K_p = K_i = 1$: $\omega_n = \sqrt{KK_i/\tau}$ | $1$ rad/s | `1.000 rad/s` | <kbd>✓ PASS</kbd> |
| **2b** | PI, $K_p = K_i = 1$: $\zeta = \frac{1+KK_p}{2\sqrt{\tau K K_i}}$ | $1$ | `1.000` | <kbd>✓ PASS</kbd> |
| **2c** | PI, $K_p = K_i = 1$: simulated overshoot | $0\%$ | `0.000%` | <kbd>✓ PASS</kbd> |
| **2d** | PI, $K_p = K_i = 1$: RK4 vs exact $1 - e^{-t}$ | $< 10^{-3}$ | `6.1e-12` | <kbd>✓ PASS</kbd> |
| **3** | Any PI: steady-state error (6 settings, both plants) | $0\%$ | `0.0000%` | <kbd>✓ PASS</kbd> |

**Independent cross-check:** the simulator was also compared against SciPy's `signal.step` for P1 (first- and second-order), P2 ($\tau_s = 0.5$ s) and P3 (exact ZOH recursion). The largest difference was $< 2 \times 10^{-4}$, and the overshoot matched to $0.01\%$.


<!-- ===================== PIECE 3 — REPLACE the "Repository Structure" block ===================== -->

```text
encs4380-dynamics-group-3/
│
├── index.html               # HW1 toolkit (Modules 1–4 + Bonus) + link to the Control section
├── control.html             # HW2 Control section: P1 PID Playground, validation, P2 Slow Sensor, P3 Digital PID, P4 Tuning Challenge
├── my-system.html           # HW2 "My System" page: our plant, spec, gains, response, Arduino code
├── README.md                # Project documentation, team roles, formulas & screenshots
├── Module1_Testing.zip      # Module 1 time response test logs & verification data
├── Module2_Testing.zip      # Module 2 frequency response calculations & tests
├── Module3_Test_Cases.pdf   # Module 3 second-order dynamics & RK4 validation report
└── Bonus_Testing.zip        # Bonus superposition distortion & Euler/RK4 stability tests
```


<!-- ===================== PIECE 4 — ADD under the existing "AI Usage Disclosure" section ===================== -->

**Homework 2 (PID Control Toolkit):**
* **Tool used:** Anthropic Claude.
* **What it was used for:** drafting the shared RK4 closed-loop simulator, the page structure of P1–P4 and My System, the Arduino code generator, and the automated validation checks.
* **What the team did:** <!-- TODO: say what you actually did, e.g. -->
  checked every validation result against hand calculations from the lecture, tested each module on desktop and phone, measured and fitted our own plant, chose and justified our spec, and reviewed the code of our own module line by line.
* Every member can explain every line of their own module during the demo.
