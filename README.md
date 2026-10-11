# Fault Detection in LVDC Microgrids (MATLAB/Simulink)

A Simulink model of a low-voltage DC (LVDC) microgrid with a fault detection method based on **conductance** and its **rate of change**. Each relay uses only its own local voltage and current, so no communication network is needed.

## System modeled

- Solar PV array with a boost DC-DC converter
- Battery with a bi-directional DC-DC converter
- Four load zones with resistive loads
- Solid state relays (SSRs) S1 to S8 along the cable

## How it works

1. Each relay measures its local voltage (v) and current (i).
2. It calculates conductance `G = i / v` and its rate of change (ROCOG).
3. If the value crosses the threshold, the relay trips.
4. A backup relay acts after a 20 ms delay if the primary relay fails.

## Tests covered

- High impedance fault (9.375 Ω) and low impedance fault (0.5 Ω)
- Faults in load zone 1 and load zone 3
- Sudden change in solar irradiation (no trip expected)

## How to run

1. Open `Fault detection in LVDC microgrid.slx` in MATLAB/Simulink (version: R2025a).
2. Set the fault resistance and fault location.
3. Click **Run** and check the scopes for relay signals and trip status.

## Author

**Bolleboina Karthikeya**
