# Final project: A digital twin with a credibility scorecard

## Overview

The final project applies the whole course to one asset chosen by the student. The asset needs at least two coupled states and one controllable input. The twin must have both data-flow arrows, a tested simulation core, calibrated parameters, at least two elements of the intelligence layer, a dashboard and a filled credibility scorecard. The project is done alone or in pairs.

## Learning outcomes assessed

The project assesses the course learning outcomes on the maturity of a twin, numerical modelling, calibration with uncertainty, the intelligence layer and verification, validation and credibility.

## Options

Each option comes with a short first step in Python. The examples run in Colab as they are and stop where the project begins.

### Option 1: A thermal asset

A heated water tank, a small greenhouse or a server rack with cooling. The fan, heater or valve is the controllable input, and temperature and energy are the states.

**A first step.** The code below simulates a heated water tank in steps of 10 seconds, with a noisy temperature sensor and a rule that switches the heater on below the target and off above it.

```python
import numpy as np

# A heated water tank: one state (temperature), one input (heater on or off)
C, k, P, T_amb = 4.2e5, 25.0, 3000.0, 20.0     # J/K, W/K, W, degrees Celsius
dt, T, target = 10.0, 20.0, 55.0
rng = np.random.default_rng(0)

for step in range(1, 1081):                     # three hours in steps of 10 s
    reading = T + rng.normal(0, 0.3)            # the sensor of the tank
    heater = 1.0 if reading < target else 0.0   # a simple on and off rule
    T += dt * (P * heater - k * (T - T_amb)) / C
    if step % 180 == 0:
        print(f"t = {step * dt / 60:5.0f} min   T = {T:5.1f} degC   heater {'on' if heater else 'off'}")
```

### Option 2: An electromechanical asset

A DC motor with thermal limits or a pump with wear. Speed, temperature and a slowly growing friction parameter are the states, and the drive voltage is the input.

**A first step.** The code below simulates the speed and the winding temperature of a small DC motor that drives a pump, with a lower voltage after four and a half minutes.

```python
import numpy as np

# A small DC motor that drives a pump: speed and winding temperature, the voltage is the input
R, K, J, b = 0.5, 0.02, 2e-4, 1e-5        # ohm, V s/rad, kg m^2, N m s/rad
load = 0.04                               # N m, the torque of the pump
C, h, T_amb = 20.0, 0.1, 25.0             # J/K, W/K, degrees Celsius
dt, omega, T = 0.01, 0.0, 25.0

for step in range(1, 60001):              # ten minutes in steps of 10 ms
    V = 12.0 if step < 27000 else 9.0     # the voltage is lowered after four and a half minutes
    i = (V - K * omega) / R               # current of the winding
    omega += dt * (K * i - b * omega - load) / J
    T += dt * (i ** 2 * R - h * (T - T_amb)) / C
    if step % 6000 == 0:
        rpm = omega * 60 / (2 * np.pi)
        print(f"t = {step * dt / 60:4.1f} min   V = {V:4.1f}   speed {rpm:5.0f} rpm   current {i:4.2f} A   T = {T:5.1f} degC")
```

### Option 3: A physiological or environmental system

A glucose and insulin model, an irrigation zone or a ventilated room with CO2. The twin must respect the safety limits of the domain and state them in the scorecard.

**A first step.** The code below simulates the carbon dioxide in a ventilated classroom, in parts per million (ppm), with a rule that raises the ventilation near the limit of 1000 ppm.

```python
# A ventilated room: CO2 concentration in ppm, the ventilation flow is the input
V, C_out, G = 150.0, 420.0, 0.005               # m^3, ppm outdoors, m^3/h of CO2 per person
dt, C = 1 / 60, 420.0                           # one-minute steps, in hours
LIMIT = 1000.0                                  # ppm, a common limit for indoor air

for minute in range(1, 241):                    # four hours
    people = 25 if 30 <= minute < 210 else 0    # a class from minute 30 to minute 210
    Q = 300.0 if C > 900 else 100.0             # ventilation in m^3/h, raised near the limit
    C += dt * (people * G * 1e6 - Q * (C - C_out)) / V
    if minute % 30 == 0:
        flag = "above the limit" if C > LIMIT else ""
        print(f"minute {minute:3d}: {people:2d} people, ventilation {Q:5.0f} m3/h, CO2 {C:6.0f} ppm {flag}")
```

## Proposal

Before starting, send a proposal of about 150 words that names the option, the dataset and the question the project answers. The proposal is optional during self-study and expected during an active delivery.

## Deliverables

The submission consists of one Colab notebook that runs from top to bottom without errors, and a technical report of 2000 to 3000 words that follows [the report template](../REPORT_TEMPLATE.md). Figures in the report must be produced by the notebook.

## Evaluation

| Criterion | Weight |
|---|---|
| Both data-flow arrows exist and are demonstrated | 20 % |
| Numerical choices are measured, not asserted | 15 % |
| Calibration includes an identifiability check and honest uncertainty | 20 % |
| The intelligence layer is validated against a baseline | 15 % |
| The scorecard contains at least two evidenced gaps | 20 % |
| Frozen configuration, seeds, fingerprints and passing tests | 10 % |

## Submission

During an active delivery of the course, the notebook and the report are sent within one week after Day 5 to utkukose@sdu.edu.tr or utkukose@gmail.com, with the subject line "VTR UGE 21 Digital Twin with Python final project".
