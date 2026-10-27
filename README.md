# Automotive CAN Bus Monitor and Fault Detector

An ESP32-based CAN bus monitoring and fault detection PCB designed using KiCad 10.0.

## Project Overview

This project focuses on designing a custom Printed Circuit Board (PCB) that interfaces an ESP32 DevKit V1 with a Controller Area Network (CAN) bus through an SN65HVD230 CAN transceiver.

The goal is to develop a platform for monitoring CAN communication, observing message traffic, and detecting selected communication anomalies through future firmware development.

This project demonstrates PCB schematic design, component selection, footprint assignment, PCB layout, and design-rule checking.

## Project Objectives

- Design a CAN bus interface PCB using KiCad.
- Interface an ESP32 with a CAN transceiver.
- Provide CANH, CANL, and ground connections.
- Include a selectable 120 Ω termination resistor.
- Plan firmware for CAN message monitoring and timeout detection.
- Document the design as part of an embedded systems portfolio.

## System Architecture

```text
External CAN Bus
   CANH / CANL / GND
          |
          v
 SN65HVD230 Transceiver
          |
          v
     ESP32 DevKit V1
          |
          v
     USB Serial Monitor
```

The ESP32 handles CAN protocol operations using its built-in TWAI controller, while the SN65HVD230 provides the physical interface to the CAN network.

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 DevKit V1 (38-pin) | Main controller |
| SN65HVD230 | CAN physical-layer transceiver |
| 120 Ω resistor | CAN bus termination |
| Termination jumper | Enables or disables termination |
| 10 kΩ resistor | Transceiver slope-control circuit |
| 100 nF capacitor | Supply decoupling |
| LED and series resistor | Power/status indication |
| 3-pin connector | CANH, CANL, and GND interface |

## Software and Tools

- KiCad 10.0 — schematic capture and PCB layout
- ESP32 development environment — planned firmware development
- GitHub — source files and project documentation

## PCB Design Workflow

1. Defined the circuit requirements.
2. Created the schematic in KiCad.
3. Selected components and assigned footprints.
4. Designed the PCB layout.
5. Ran Electrical Rules Checker (ERC).
6. Ran Design Rules Checker (DRC).
7. Organized the project files for documentation and version control.

## Planned Firmware Features

The following features are planned and have not yet been validated:

- Receive CAN frames.
- Display CAN identifiers and data bytes.
- Monitor message frequency.
- Detect missing periodic messages using configurable timeouts.
- Report selected communication errors.
- Log received frames through the USB serial interface.

## Repository Structure

```text
Automotive_CAN_Monitor/
├── KiCad/
│   ├── Automotive_CAN_Monitor.kicad_pro
│   ├── Automotive_CAN_Monitor.kicad_sch
│   └── Automotive_CAN_Monitor.kicad_pcb
├── Images/
│   ├── schematic.png
│   ├── pcb-layout.png
│   ├── erc-results.png
│   └── drc-results.png
├── Documentation/
│   └── component-list.md
└── README.md
```

*The filenames shown are the intended organization. Include only files and screenshots that actually exist in your repository.*

## Design Verification

The schematic and PCB were checked using KiCad ERC and DRC.

A zero-error result indicates that the reported checks passed under the configured rules. It does not guarantee correct electrical operation, successful CAN communication, or automotive-grade reliability.

The design has not been physically manufactured or tested.

## Current Project Status

 Schematic design
 Component selection
 Footprint assignment
 PCB layout
 ERC and DRC checks performed
 Final electrical and footprint review


## Future Improvements

- Develop CAN monitoring firmware.
- Test communication using a separate CAN test node.
- Add a CAN message logging utility.
- Improve documentation with verified schematics and layout images.
- Review protection circuitry and physical connector dimensions.

## Applications

- Embedded systems learning
- Automotive electronics education
- CAN communication experimentation
- PCB design and hardware development portfolio

## Disclaimer

This is an educational prototype, not an automotive-qualified diagnostic device. It has not been manufactured or validated for installation in a real vehicle. Testing should initially be performed using a controlled CAN bench setup.

