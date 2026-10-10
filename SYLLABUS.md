# Syllabus: Digital Twin with Python

## Course information

| Item | Detail |
|---|---|
| Course | Digital Twin with Python |
| Code | VTR UGE 21, value added course |
| Institution | Vel Tech Rangarajan Dr. Sagunthala R&D Institute of Science and Technology, Chennai, India |
| Credits | L-T-P-C 1-0-0-1 |
| Format | Five days, one module per day, synchronous sessions with materials for asynchronous study |
| Instructor | Prof. Dr. Utku Kose |
| Language | English |

## Course description

A digital twin is a virtual counterpart of a specific physical asset that is kept in step with it by data and, in its full form, acts back on it . The course builds one complete software twin in five days, always of the same asset: A 48 V lithium-ion battery pack with electrical, thermal and ageing dynamics on three time scales. Day 1 measures the difference between a digital model, a digital shadow and a digital twin and sets up a reference architecture . Day 2 builds the simulation core and tests it, Day 3 turns noisy telemetry into calibrated parameters, Day 4 adds surrogates, hybrid models, anomaly detection, prognostics and control , and Day 5 adds the dashboard, the logs and a credibility assessment . The asset and every sensor are simulated, which is how digital twins are developed before hardware is available, and the limits of that approach are stated as part of the course.

## Prerequisites

No programming experience is required. Basic secondary-school mathematics and physics are assumed: Functions and graphs, rates of change and the idea of energy balance. Students without programming experience should complete the start-here notebook before Day 1.

## Learning outcomes

On completion, students are expected to distinguish a digital model, a digital shadow and a digital twin by their data flows and measure the difference, to write a physical model with stated assumptions and integrate it with a method whose order and stability they have verified, to build a telemetry pipeline and identify model parameters with an identifiability check and honest uncertainty, to add a surrogate, a hybrid model, a residual-based anomaly detector, a prognostic and a closed-loop controller, each measured against a baseline, and to assemble the whole into one twin with a dashboard, logs and a credibility scorecard. In Python, students are expected to use variables, lists, loops, functions and dictionaries, NumPy arrays, pandas data frames with time indices, Matplotlib plots, the scikit-learn interface, classes and dataclasses.

## Daily plan

| Day | Module | Python step |
|---|---|---|
| 1 | Concept and Architecture | Values, variables, lists and decisions |
| 2 | Simulation Foundations in Python | NumPy arrays and functions that receive functions |
| 3 | Data Pipelines and Model Calibration | pandas data frames and time |
| 4 | Intelligence Layer of the Twin | Plots and the scikit-learn interface |
| 5 | Visualization and Capstone Development | Classes, records and files |

## Learning activities and workload

Each day combines about three hours of synchronous session with about three to five hours of individual work on the notebook, the lab, the challenges and the daily task. In asynchronous study, the study path of each day gives a suggested time for every activity, about six to eight hours per day in total. The final project needs about twenty hours.

## Assessment

Assessment rests on a final project, a working digital twin of an asset of the student's choice with a credibility scorecard, which consists of a coding application and a short technical report. Each day also offers an optional task, an optional research and report assignment and a self-assessment in the lab. During an active delivery of the course, components and weights are announced by the instructor at the start of the course in line with the regulations of Vel Tech University, and the daily task can be sent together with the exported learning log to utkukose@sdu.edu.tr or utkukose@gmail.com. The self-assessments are formative and do not count towards the grade.

## Policy on generative AI tools

Generative AI tools may be used for explanation, debugging and drafting, under three conditions. Every use is declared in the statement on tools of the report, every output that enters the submitted work is checked by the student, and every reference is verified against its source. A fabricated reference, a fabricated result or undeclared generated text is treated as a breach of academic integrity.

## Academic integrity

Work submitted for assessment must be the student's own. Collaboration in class is encouraged, while code and reports for the final project are written individually or by the declared pair. Sources are cited for every idea, figure, dataset and piece of code taken from others.

## Accessibility

All pages run in a browser without installation and work on phones. Labs can be used with the keyboard, and animations respect the reduced-motion setting of the operating system. Lecture notes are also provided as PDF.

## Main textbooks and open resources

The course is self-contained, and every source is cited where it is used. Useful open companions are the documentation of SciPy, NumPy, pandas and scikit-learn, and the ISO 23247 framework for digital twins in manufacturing.
