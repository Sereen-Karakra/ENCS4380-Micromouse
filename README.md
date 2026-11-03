# ENCS4380 Homework 1: Dynamic Characteristics Interactive Toolkit

Interactive web toolkit that makes the dynamic characteristics of sensors visible (first-order and second-order response). Built for ENCS4380 Interfacing Techniques, Birzeit University (Instructor: Dr. Wasel Ghanem).

**Live site:** https://sereen-karakra.github.io/encs4380-dynamics-42/

## Team

| Member | Responsibility | Issue | Status |
|---|---|---|---|
| Maysam Abu Eid | Module 1: First-order time response | #2 | Done (live) |
| Dania Abu Ayyash | Module 2: First-order frequency response | | In progress |
| Sereen Karakra | Module 3: Second-order response | | Done |
| Raneem Khawaja | Module 4: "Guess the sensor" challenge | | Planned |
| Masa Awad | Bonus work | | Planned |

## Modules

### Module 1: First-order time response (`index.html`)
Thermometer model: τ·dy/dt + y = K·x(t), G(s) = K / (τs + 1).

- Sliders for gain K, time constant τ, and input amplitude/ramp rate; input type is step or ramp.
- Time-domain plot that redraws instantly (input, ideal output, sensor output).
- Step: markers at t = τ (63.2% of KA) and t = 3τ (95% of KA).
- Ramp: lag = τ and steady-state error = K·A·τ, shown on the plot and in the metrics.
- Error-fraction plot: ln(e(t)/e(0)) against t is a straight line with slope −1/τ; the measured slope is compared with the theory.
- "Predict, then check" box: the user picks an answer first, then checks it.
- Validation table with expected value, measured value, and PASS/FAIL.

Validation checks currently passing on the page: y(τ) = 0.632·KA, y(3τ) = 0.95·KA, ramp steady-state error = K·A·τ, ramp lag = τ, log-plot slope = −1/τ.

### Module 2: First-order frequency response
In progress (due Mon 9 Nov 2026).

### Module 3: Second-order response (`module3.html`)
Done. See the page for details.

### Module 4: "Guess the sensor" challenge
Planned (due Thu 12 Nov 2026).

## Screenshots

_Add screenshots here after each module is final._

## Technical notes

- Static site on GitHub Pages: plain HTML and JavaScript, no server or login needed.
- Plots use the closed-form responses from the lecture slides, drawn with [Chart.js](https://www.chartjs.org/).
- Work is tracked with one GitHub Issue per module, assigned to its owner.

## AI use

We used an AI assistant (Claude) as allowed by the homework. Maysam used it to review the Module 1 code and fix errors (ramp steady-state error for K ≠ 1, the error-fraction plot, markers, and the validation table), and to help write the issue and this README. Every member must be able to explain their own code and equations in the demo.

_Other members: add what you used AI for._

## Timeline

| Date | Milestone |
|---|---|
| Tue 3 Nov 2026 | Checkpoint 1: Pages live, Module 1 working |
| Mon 9 Nov 2026 | Checkpoint 2: Modules 2 and 3 working |
| Thu 12 Nov 2026 | Final release v1.0 |
| Sun 15 and Mon 16 Nov 2026 | Group demos |
