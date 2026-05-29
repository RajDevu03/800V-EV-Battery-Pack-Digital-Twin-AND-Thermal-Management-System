# 800V-EV-Battery-Pack-Digital-Twin-AND-Thermal-Management-System
A high-fidelity MATLAB/Simulink digital twin of an 800V (240S10P) electric vehicle battery pack, featuring an active liquid thermal management system and dynamic drive cycle testing.

## 📌 Overview

This repository contains a system-level digital twin of a high-performance 800V electric vehicle battery pack. Developed using Model-Based Design (MBD) principles, this simulation evaluates both the electrical discharge characteristics and the 3D thermal gradients of the pack under realistic, transient driving conditions.

The project demonstrates the intersection of electrical load demands and fluid heat transfer, providing predictive analysis for battery range and thermal safety without the need for physical prototyping.

## ⚡ Technical Architecture

* **High-Voltage Pack:** A dense 240S10P cylindrical cell configuration engineered via the Simscape Battery Builder App, modeling an industry-standard "skateboard" chassis layout.
* **Thermal Management System (TMS):** An integrated active liquid cooling loop (incorporating a pump, radiator heat exchanger, and specific coolant fluid properties) paired with a passive convective air network to extract heat and mitigate thermal runaway.
* **Dynamic Load Simulation:** Incorporates a custom 340-second real-world drive cycle—featuring 250A hard launches, steady highway cruising, and aggressive -100A regenerative braking—translated into physical signals via Simulink-PS converters.

## 📊 Key Simulation Results

* **Thermal Validation:** Successfully extracted cell-level temperature arrays, proving the efficacy of the bottom-cooling plate. The simulation clearly illustrates the thermal gradient between the hotter inner cells and the cooler outer cells during peak $I^2R$ (Joule heating) loads.
* **Range Estimation:** Validated State of Charge (SOC) drain rates. The transient load simulation resulted in a 1.6% capacity drain over 5.6 minutes of aggressive driving, mathematically scaling to an estimated real-world ~348-mile continuous highway range.

## 🛠️ Tools & Technologies

* **MATLAB & Simulink**
* **Simscape Battery**
* **Simscape Fluids (Thermal Liquid)**
* **Signal Editor**

## 🚀 How to Run the Simulation

1. Clone the repository and open the main `.slx` model file in MATLAB/Simulink.
2. Ensure the **Simscape Battery** and **Simscape Fluids** toolboxes are installed in your MATLAB environment.
3. Open the `Signal Editor` block to view, modify, or input custom `[Time]` and `[Data]` arrays for new drive cycles.
4. Set the simulation Stop Time to match the length of your drive cycle (e.g., `340` seconds).
5. Run the simulation.
6. Open the connected `Scope` blocks to visualize the real-time SOC degradation and 3D cell temperature gradients.

---

*Developed as a graduate-level Electrical and Computer Engineering portfolio project at Saint Louis University.*
