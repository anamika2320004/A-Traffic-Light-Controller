# Traffic Light Controller (FSM)

## Project Overview
This project implements a **Traffic Light Controller** using a **Finite State Machine (FSM)** in Verilog.  
It simulates a simple traffic light system with three lights: **Green, Yellow, and Red**.  
The FSM manages the sequence and timing of the lights and can be visualized using **EPWave** in EDA Playground.

---

## Features
- 3-state FSM: **Green → Yellow → Red → Green**  
- Configurable timing for each light  
- Sequential and combinational logic implementation  
- EPWave waveform visualization supported  
- Easy to extend for pedestrian signals or multiple intersections  

---

## FSM State Table

| State | Light ON | Next State |
|-------|----------|------------|
| S0    | Green    | S1 (Yellow) |
| S1    | Yellow   | S2 (Red)    |
| S2    | Red      | S0 (Green)  |

---

## Files Included

| File Name             | Description                                |
|-----------------------|--------------------------------------------|
| `txt file`     | Verilog design of the Traffic Light FSM and  Testbench for simulation with EPWave output  |
---

## Console Output (Example)

| Time      | Red | Yellow | Green |
|-----------|-----|--------|-------|
| 0         | 0   | 0      | 1     |
| 65000     | 0   | 1      | 0     |
| 95000     | 1   | 0      | 0     |
| 155000    | 0   | 0      | 1     |

---

## How to Run on EDA Playground
1. Go to [EDA Playground](https://www.edaplayground.com/).  
2. Create a new project and select **Icarus Verilog** as the simulator.  
3. Copy `txt file` for code and testbench into the editor.  
4. Ensure the testbench contains:
   ```verilog
   $dumpfile("dump.vcd");
   $dumpvars(0, tb_traffic_light);
5. Run the simulation.
6. Open EPWave to view the Red, Yellow, and Green signals over time.

   Notes-

Timing parameters in code can be adjusted:

parameter GREEN_TIME = 5;
parameter YELLOW_TIME = 2;
parameter RED_TIME = 5;


FSM loops indefinitely: Green → Yellow → Red → Green.
