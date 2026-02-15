# 🏭 Batch Reactor Control System

## 📋 Project Overview
A simulation of a chemical batch reactor control system implemented in **CODESYS V3.5** using **Structured Text (ST)**.
The project simulates physical process dynamics (heating, cooling logic) and features a priority-based safety system.

## ⚙️ Key Features

### 1. Sequential Control (State Machine)
Implemented a robust state machine handling the full process lifecycle:
- **IDLE:** System waiting for start command.
- **FILLING:** Valve control based on level sensors.
- **HEATING/MIXING:** Temperature regulation with hysteresis.
- **DRAINING:** Emptying the tank after successful cycle.

### 2. Safety Logic (Interlocks) 🚨
Safety is decoupled from the main process logic to ensure reliability.
- **Overheat Protection:** Hard shutdown if Temp > 100°C.
- **Emergency Stop:** Immediate valve closure and mixer stop (Hard Kill).
- **Sensor Failure Simulation:** Logic handles invalid analog inputs.

### 3. HMI Visualization
- Real-time tank level animation.
- Trend recording for Temperature/Level.
- Alarm table for critical events.
- Manual/Auto mode switch.

## 💻 Code Structure
- `PRG_Main`: Main sequencer (CASE statement).
- `PRG_Safety`: Independent safety monitoring.
- `FB_TankSim`: Physics simulation block (First-Order Lag).

## 🚀 How to Run
1. Open `Batch_Reactor.project` in CODESYS V3.5.
2. Build and Download to **Control Win V3 x64** (SoftPLC).
3. Open visualization `VIS_Main`.
4. Press **START**.
