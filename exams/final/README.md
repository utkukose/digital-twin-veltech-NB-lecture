# Final project: A digital twin with a credibility scorecard

## Overview

The final project applies the whole course to one asset chosen by the student. The asset needs at least two coupled states and one controllable input. The twin must have both data-flow arrows, a tested simulation core, calibrated parameters, at least two elements of the intelligence layer, a dashboard and a filled credibility scorecard. The project is done alone or in pairs.

## Learning outcomes assessed

The project assesses the course learning outcomes on the maturity of a twin, numerical modelling, calibration with uncertainty, the intelligence layer and verification, validation and credibility.

## Options

### Option 1: A thermal asset

A heated water tank, a small greenhouse or a server rack with cooling. The fan, heater or valve is the controllable input, and temperature and energy are the states.

### Option 2: An electromechanical asset

A DC motor with thermal limits or a pump with wear. Speed, temperature and a slowly growing friction parameter are the states, and the drive voltage is the input.

### Option 3: A physiological or environmental system

A glucose and insulin model, an irrigation zone or a ventilated room with CO2. The twin must respect the safety limits of the domain and state them in the scorecard.

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
