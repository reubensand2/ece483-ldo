# Low-Dropout Regulator Design

A transistor-level low-dropout regulator designed and simulated in Cadence
Virtuoso with Timothy Fong for UIUC ECE 483: Analog IC Design. We worked
collaboratively throughout the project, from topology selection and transistor
sizing through compensation, simulation, and performance analysis.

The design uses a PMOS pass device to reduce dropout voltage and regulates a
nominal 1.8 V supply to 1.2 V across a 0.1 mA to 10 mA load range. A
Miller-compensated error amplifier and series zero-nulling resistor maintain
closed-loop stability across the full load range.

## Highlights

- 1.2 V regulated output from a 1.8 V ±10% input
- PMOS pass-device topology with resistive feedback
- 0.1 mA to 10 mA supported load range
- 4.83 µV/mA simulated load regulation
- 5.87 µV/V and 11.13 µV/V simulated line regulation at light and heavy load
- 94.75 dB and 90.53 dB DC loop gain at light and heavy load
- 1.25 MHz and 1.46 MHz unity-gain frequency
- 61.1° and 100.2° phase margin across the load extremes
- Approximately -63.8 dB power-supply rejection at 1 kHz

For the schematic, design rationale, transistor operating points, stability
analysis, and complete simulation results, see the
[final project report](ldo_report.pdf).

## Analysis Workflow

Simulation data was exported from Cadence and post-processed in Python using
pandas, NumPy, and Matplotlib. The notebook calculates regulation slopes and
stability metrics and produces the load-regulation, line-regulation, loop-gain,
phase, and power-supply-rejection plots used in the report.

## Repository Contents

- `ldo_report.pdf` — complete design and simulation report
- `plotting/ldo_plots.ipynb` — analysis and visualization notebook
- `plotting/*.csv` — selected exported simulation data
- `plotting/*.png` — exported regulation plots
- `plotting/dc_op_ldo.txt` — transistor operating-point data consumed by the
  notebook

The Cadence design database, proprietary device models, and course simulation
environment are intentionally omitted, so the repository is not distributed 
as a standalone reproducible Virtuoso project.
