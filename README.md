# traffic-light-control-system
A modular Traffic Light Control System implemented in Verilog HDL using a clean separation of **Datapath** and **Controller (FSM)**. This project simulates a real-world four-state traffic intersection using finite state machines, counters, and synchronized light control.

---

## 📁 Project Structure
traffic_control_system/
├── src/
│ ├── controller.v # FSM controller (Moore Machine)
│ ├── datapath.v # Light register logic
│ ├── timer_counter.v # Counter + comparator logic
│ └── top_traffic_controller.v # Top module to instantiate all components
├── testbench/
│ └── traffic_tb.v # Simulation testbench
├── README.md
└── waveform.vcd # Generated during simulation (optional)

---

## ⚙️ System Description

This traffic control system operates in a 4-phase cycle:

| State | Main st Light | Cross st Light |
|-------|----------|----------|
| S0    | Green    | Red      |
| S1    | Yellow   | Red      |
| S2    | Red      | Green    |
| S3    | Red      | Yellow   |

- The **controller** is a Moore FSM that changes states based on a timing signal.
- The **counter** and **comparator** work together to time each state.
- The **datapath** uses light registers and decodes the FSM state into light control outputs.

---

## 🧠 Functional Units

- `State Register` – Stores current traffic light state
- `Counter` – Increments each clock cycle until threshold
- `Comparator` – Checks if time is expired for a state
- `Light Registers` – Hold 3-bit RGB signals for NS and EW
- `Multiplexer` – Maps FSM state to corresponding light pattern

---

## 📦 Features

- Modular Verilog design (datapath/controller separation)
- Parameterized timing (green/yellow durations)
- FSM-driven logic (Moore machine)
- Easily extensible for pedestrian or sensor-based control
- Simulatable with any Verilog-compatible tool (Icarus Verilog, etc.)

---


