# 🏭 Factory IO – Level Control with PID & WinCC HMI/SCADA

> A simulation-based industrial automation project using **Factory IO** and **Siemens WinCC (SIMATIC HMI)**, focused on real-time liquid level control with PID regulation and a fully developed 3-screen HMI interface.

---

## 📋 Project Overview

This project simulates a **liquid level control system** in Factory IO, where a PID controller continuously regulates the fill level of a tank. The simulation includes a level meter, fill valve, discharge valve, and flow meter — all wired to a virtual PLC via S7-PLCSIM.

The primary focus of this project is the **HMI development in Siemens WinCC**, featuring a structured 3-screen interface built for real operator use: a process overview (Tank Screen), a control panel (Control Screen), and a live data monitor (Data Monitor Screen).

---

## 🖥️ HMI Interface – 3-Screen Architecture

### 🟦 Screen 1 – Tank Screen (Process Overview)
![Tank Screen](screenshots/tank_screen.png)

The main process view gives operators a live graphical overview of the system:
- **Animated tank** with a real-time fill level bar (0–300 cm scale)
- **Live tag displays** for Level Meter (cm) and Fill Valve (%)
- Graphical representation of the **Discharge Valve** and **Flow Meter**
- Dynamic background styled to match an industrial environment
- Navigation buttons to switch between all three screens

---

### 🟩 Screen 2 – Control Screen (Operator Panel)
![Control Screen](screenshots/control_screen.png)

The operator control panel for managing the PID process:
- **Display Setpoint (SP)** – shows the target level value
- **Display Present Value (PV)** – shows the actual measured tank level
- **Start / Stop buttons** – initiates or halts the fill flow
- **Error Indicator** – visual alarm lamp for fault detection
- Clean layout with high-contrast labels for industrial readability

---

### 🟨 Screen 3 – Data Monitor Screen (Trend & Logging)
![Data Monitor Screen](screenshots/data_monitor_screen.png)

A dedicated trend and data logging screen for process analysis:
- **WinCC TrendControl** displaying real-time trends for:
  - `Tank-Level` (linked to `Global_DB`)
  - `Fill-Valve` (linked to `Global_DB`)
- Dual Y-axis scale (0–100 left / 0–300 right) for simultaneous monitoring
- Playback controls for reviewing historical data
- Tag connection table with live **Value** and **Date/Time** columns
- Timestamped logging (e.g. `2/26/2026 3:17:36 PM`)

---

## 🔬 Factory IO Simulation Scene
![Factory IO Scene](screenshots/factory_io_scene.png)

The physical simulation was built in Factory IO using the **Level Control** scene:
- Transparent upper tank with a visible **level gauge**
- **Fill valve** mounted on the tank inlet
- **Discharge valve** and **flow meter** at the base
- Lower reservoir for recirculating liquid
- Connected to S7-PLCSIM via Siemens S7 driver

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Factory IO** | 3D process simulation (Level Control scene) |
| **Siemens WinCC (SIMATIC HMI)** | HMI development – screens, trends, tags |
| **TIA Portal + S7-PLCSIM** | PLC programming & virtual simulation |
| **Global DB (Data Block)** | Tag storage for PID values and process data |
| **PID Controller** | Automated level regulation |

---

## 🔄 System Architecture

```
Factory IO (3D Level Control Simulation)
        │
        ▼
  S7-PLCSIM (Virtual S7 PLC)
  ┌──────────────────────────────┐
  │  PID Control Block           │
  │  Global DB (SP, PV, Valves)  │
  └────────────┬─────────────────┘
               │
               ▼
    WinCC Runtime (SIMATIC HMI)
  ┌────────────────────────────────────┐
  │  Tank Screen    – Process overview │
  │  Control Screen – SP/PV + Start    │
  │  Data Monitor   – Trends & Logging │
  └────────────────────────────────────┘
```

---

## 📸 Screenshots

```
/screenshots
  ├── factory_io_scene.png       # Factory IO 3D simulation
  ├── control_screen.png         # HMI Control Screen (SP, PV, Start/Stop)
  ├── data_monitor_screen.png    # HMI Data Monitor (Trend graphs + logging)
  └── tank_screen.png            # HMI Tank Screen (animated process view)
```

---

## 📚 Key Learning Outcomes

- Designed a structured **3-screen HMI project** in WinCC from scratch
- Connected WinCC tags to a **Global Data Block** for real-time PLC data exchange
- Configured **TrendControl** with dual Y-axis scaling for multi-variable monitoring
- Built operator-facing controls (SP input, Start/Stop, Error indicator)
- Applied industrial HMI layout principles: clear navigation, contrast, and labeling
- Integrated a PID control loop with full operator visibility through the SCADA interface

---

## 🚀 How to Run

1. Open the Factory IO scene: `Level_Control.factoryio`
2. Connect Factory IO to **S7-PLCSIM** via the Siemens S7-PLCSIM driver
3. Load the **TIA Portal** project and start the PLC simulation
4. Launch **WinCC Runtime** to open the HMI
5. Navigate to the **Control Screen**, set a Setpoint (SP), and press **Start**
6. Monitor live PID response on the **Tank Screen** and **Data Monitor Screen**

---

## 📁 Repository Structure

```
📦 FactoryIO-LevelControl-SCADA
 ┣ 📂 FactoryIO/              # Factory IO scene file (.factoryio)
 ┣ 📂 TIA_Portal/             # PLC project (PID block + Global DB)
 ┣ 📂 WinCC/                  # WinCC project (3 screens + tag config)
 ┣ 📂 screenshots/            # HMI and simulation screenshots
 ┗ 📄 README.md
```

---

*Project developed as part of automation and instrumentation studies — with emphasis on HMI/SCADA design using Siemens WinCC and SIMATIC HMI.*
