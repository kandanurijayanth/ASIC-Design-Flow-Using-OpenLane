# ASIC Design Flow Using OpenLane 2.3.10

![OpenLane](https://img.shields.io/badge/OpenLane-v2.3.10-blue)
![Sky130](https://img.shields.io/badge/PDK-Sky130-success)
![Verilog](https://img.shields.io/badge/Language-Verilog-orange)
![Status](https://img.shields.io/badge/Flow-Completed-brightgreen)

A complete **RTL-to-GDSII implementation** of a **4-bit Synchronous Counter** using the **OpenLane 2.3.10** open-source ASIC design flow and the **Sky130 Process Design Kit (PDK)**.

This project demonstrates the complete ASIC physical design flow from **Verilog RTL** to a manufacturable **GDSII layout** using modern open-source EDA tools.

---

# Project Overview

The objective of this project is to understand and implement the complete RTL-to-GDSII ASIC design flow using OpenLane.

The design was successfully:

- RTL Verified
- Synthesized
- Floorplanned
- Power Planned
- Placed
- Clock Tree Synthesized
- Routed
- Verified (DRC, LVS, Antenna)
- Exported as GDSII

---

# Design Specifications

| Parameter | Value |
|-----------|-------|
| Design | 4-bit Synchronous Counter |
| RTL Language | Verilog HDL |
| PDK | Sky130 |
| ASIC Flow | OpenLane 2.3.10 |
| Operating Clock | 10 ns |
| Reset | Active High |
| Output | 4-bit Counter |

---

# Tools Used

| Tool | Purpose |
|------|---------|
| Verilog HDL | RTL Design |
| Verilator | RTL Linting |
| Yosys | Logic Synthesis |
| OpenROAD | Physical Design |
| OpenLane 2.3.10 | Complete ASIC Flow |
| Magic | DRC & LVS Verification |
| KLayout | Layout Visualization |
| Docker | Tool Environment |
| Ubuntu (WSL2) | Development Environment |

---

# ASIC Design Flow

```
RTL Design
      │
      ▼
Verilator Lint
      │
      ▼
Logic Synthesis
      │
      ▼
Floorplanning
      │
      ▼
Power Distribution Network
      │
      ▼
Global Placement
      │
      ▼
Detailed Placement
      │
      ▼
Clock Tree Synthesis
      │
      ▼
Routing
      │
      ▼
Design Rule Check
      │
      ▼
Layout Versus Schematic
      │
      ▼
Antenna Check
      │
      ▼
GDSII Generation
```

---

# RTL Design

The implemented RTL is a **4-bit Synchronous Binary Counter**.

### Features

- Positive-edge triggered
- Active-high asynchronous reset
- Counts from **0 to 15**
- Automatically wraps to **0**

### RTL Screenshot

<img width="502" height="392" alt="01_RTL Design" src="https://github.com/user-attachments/assets/c58cbeac-e7bd-4393-bc64-4143144ff600"/>

---

# Repository Structure

```
ASIC-Design-Flow-Using-OpenLane
│
├── RTL
│   └── counter4.v
│
├── Config
│   ├── config.yaml
│   ├── pin_order.cfg
│   ├── impl.sdc
│   └── signoff.sdc
│
├── Layout
│   ├── counter4.gds
│   ├── counter4.def
│   ├── counter4.lef
│   ├── counter4.mag
│   └── counter4.v
│
├── Reports
│   ├── stat.rpt
│   ├── flow.log
│   └── manufacturability.rpt
│
├── Screenshots
│   ├── 01_RTL_Design.png
│   ├── 02_OpenLane_Flow.png
│   ├── 03_Synthesis_Report.png
│   ├── 04_Floorplan.png
│   ├── 05_PDN.png
│   ├── 06_Global_Placement.png
│   ├── 07_Detailed_Placement.png
│   ├── 08_CTS.png
│   ├── 09_Routing.png
│   ├── 10_Final_GDS.png
│   ├── 11_Zoomed_Layout.png
│   └── 12_DRC_LVS_Antenna.png
│
└── README.md
```

---

# Results

## 1. OpenLane Flow

### Execution Summary

- Flow Status : ✅ Completed Successfully
- Total Stages : **78/78**
- PDK : Sky130
- OpenLane Version : 2.3.10

### Screenshot

> Replace the link below with your OpenLane Flow screenshot.

<img src="YOUR_OPENLANE_FLOW_IMAGE_LINK" width="850"/>

---

## 2. Logic Synthesis

The RTL was synthesized using **Yosys**.

Generated Outputs:

- Gate-level Netlist
- Cell Statistics
- Area Report

<img width="604" height="592" alt="03_synthesis_Report" src="https://github.com/user-attachments/assets/5cfbf938-aa4d-43f5-bd11-78f472418572"/>

---

## 3. Floorplanning

The die area and core area were generated during the floorplanning stage.

<img width="601" height="899" alt="04_Floorplan" src="https://github.com/user-attachments/assets/52d9fe0c-fc8b-48a9-b405-04435b57b6e5"/>

---

## 4. Power Distribution Network (PDN)

Power rails and power distribution network were generated successfully.

<img width="529" height="885" alt="05_PDN" src="https://github.com/user-attachments/assets/7f714896-21f7-455f-acc3-6d27871d4c8b"/>

---

## 5. Global Placement

Standard cells were placed inside the core area.

<img width="545" height="895" alt="06_Global Placement" src="https://github.com/user-attachments/assets/22123308-1e69-4a77-af7d-6bb17b826223"/>

---

## 6. Detailed Placement

Cells were legally placed with optimized utilization.

<img width="542" height="881" alt="07_Detailed Placement" src="https://github.com/user-attachments/assets/56df23b5-4714-46a2-8672-8afcc8c6f1d3"/>

---

## 7. Clock Tree Synthesis (CTS)

Clock buffers were inserted to minimize clock skew.

<img width="565" height="894" alt="08_CTS" src="https://github.com/user-attachments/assets/3d1cb6c7-008a-4cf5-86b0-b438a79a7547"/>

---

## 8. Routing

Signal routing completed successfully.

<img width="550" height="896" alt="09_Routing" src="https://github.com/user-attachments/assets/5286db46-2986-4048-8496-8cb013cc7aed"/>

---

## 9. Final GDS Layout

Final manufacturable GDSII layout generated by OpenLane.

<img width="559" height="884" alt="10_Final_GDS" src="https://github.com/user-attachments/assets/bf13ace9-ee22-44a8-9a23-b55852691863"/>

---

## 10. Zoomed Layout

Zoomed-in view showing routing and standard cells.

<img width="955" height="871" alt="11_Zoomed Layout" src="https://github.com/user-attachments/assets/1e8a5f58-0f72-4971-a681-63ee72988690"/>

---

# Verification Results

## Design Rule Check (DRC)

✅ Passed

<img width="300" alt="DRC Passed" src="https://github.com/user-attachments/assets/d920d01a-3023-45f8-9e83-44b46842107a"/>

---

## Layout Versus Schematic (LVS)

✅ Passed

<img width="300" alt="LVS Passed" src="https://github.com/user-attachments/assets/a81f1f6b-dce7-4f65-adf8-81259043aabc"/>

---

## Antenna Check

✅ Passed

<img width="300" alt="Antenna Passed" src="https://github.com/user-attachments/assets/c6d8edfc-6aee-4d9f-96d5-99c497841a7a"/>

---

# Synthesis Statistics

| Parameter | Value |
|-----------|-------|
| Number of Ports | 3 |
| Number of Wires | 13 |
| Number of Cells | 14 |
| Chip Area | 178.9216 µm² |

---

# Final Outputs

The OpenLane flow generated the following physical design files:

```
counter4.gds
counter4.def
counter4.lef
counter4.mag
counter4.v
counter4.sdc
counter4.spef
counter4.lib
```

---

# Achievements

- ✅ RTL Design Completed
- ✅ Verilator Lint Passed
- ✅ Logic Synthesis Completed
- ✅ Floorplanning Completed
- ✅ Power Distribution Network Generated
- ✅ Global Placement Completed
- ✅ Detailed Placement Completed
- ✅ Clock Tree Synthesis Completed
- ✅ Routing Completed
- ✅ DRC Passed
- ✅ LVS Passed
- ✅ Antenna Check Passed
- ✅ GDSII Generated Successfully

---

# Learning Outcomes

This project provided hands-on experience with:

- RTL Design using Verilog
- ASIC RTL-to-GDSII Flow
- Logic Synthesis using Yosys
- Floorplanning
- Power Planning
- Cell Placement
- Clock Tree Synthesis
- Routing
- DRC Verification
- LVS Verification
- Antenna Checking
- GDSII Generation
- OpenLane & OpenROAD Toolchain
- Sky130 Process Design Kit

---

# Future Improvements

- Design larger digital circuits
- Implement a pipelined processor
- Explore low-power ASIC design techniques
- Perform timing optimization
- Multi-clock domain implementation

---

# Conclusion

This project successfully demonstrates the complete RTL-to-GDSII implementation of a **4-bit Synchronous Counter** using **OpenLane 2.3.10** and the **Sky130 PDK**.

The design was successfully synthesized, floorplanned, power planned, placed, clock-tree synthesized, routed, and verified. The final layout passed **DRC**, **LVS**, and **Antenna** verification, resulting in a manufacturable **GDSII** layout.

This project provides practical hands-on experience with modern open-source ASIC physical design tools and serves as a strong foundation for implementing more complex digital VLSI systems.

---

# Repository Topics

```
verilog
asic
vlsi
openlane
openroad
yosys
sky130
physical-design
rtl-to-gdsii
klayout
magic-vlsi
docker
```

---

# Author

**Kandanuri Jayanth**
