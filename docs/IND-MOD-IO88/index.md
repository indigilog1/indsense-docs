# IND-MOD-IO88

## Electrical Safety

!!! danger "Risk of Electric Shock"

    The IND-MOD-IO88 is intended for use with industrial control systems. Incorrect installation or wiring may result in electric shock, equipment damage, or personal injury.

    - Disconnect all power sources before installing or servicing the module.
    - Verify that the power supply is turned off before making or modifying any wiring connections.
    - Never touch exposed conductors while the system is energized.

!!! warning "Qualified Personnel Only"

    Installation, commissioning, and maintenance of this product must only be performed by qualified personnel familiar with industrial electrical systems and local electrical safety regulations.

!!! warning "Observe Voltage Ratings"

    Ensure that all input voltages, output loads, and power supply connections remain within the specifications provided in this manual. Exceeding the maximum ratings may permanently damage the module.

!!! caution "Wiring"

    - Use appropriately sized wires and tighten terminal screws securely.
    - Verify wiring polarity before applying power.
    - Keep signal wiring separate from high-voltage or high-current cables to reduce electrical noise.

!!! info "Regulatory Compliance"

    Follow all applicable local electrical codes and safety standards when installing and operating the IND-MOD-IO88.

## Introduction  

The **IND-MOD-IO88** is a compact industrial **Modbus RTU 8-channel I/O Module** designed to simplify the integration of digital inputs and outputs into PLC, SCADA, HMI, and Industrial IoT systems. It communicates over the industry-standard **RS-485** interface using the **Modbus RTU** protocol, ensuring reliable interoperability with a wide range of industrial automation equipment.

The module provides **8 opto-isolated digital inputs** and **8 opto-isolated digital outputs**, making it suitable for monitoring field devices such as push buttons, limit switches, proximity sensors, and relay contacts, while simultaneously controlling loads including relays, contactors, indicator lamps, solenoid valves, and other industrial actuators.

Designed for demanding industrial environments, the IND-MOD-IO88 supports both **dry-contact** and **wet-contact (up to 24 VDC)** digital inputs (NPN or PNP) with built-in bidirectional optocoupler and 8 Digital Outputs supports upto 40V, open-drain output, output load 500mA/channel(MAX) allowing seamless integration with a wide variety of sensors and control devices. The robust RS-485 communication interface enables reliable long-distance communication in electrically noisy environments.

Whether used as a distributed remote I/O module, a PLC expansion module, or an interface between field devices and Industrial IoT gateways, the IND-MOD-IO88 offers a cost-effective, reliable, and easy-to-deploy solution for industrial automation applications.

### Key Features

* 8 opto-isolated digital inputs
* Supports both dry-contact and wet-contact inputs (up to 24 VDC)
* 8 opto-isolated digital outputs for controlling external loads
* RS-485 communication with Modbus RTU protocol
* Compatible with PLCs, HMIs, SCADA systems, and Industrial IoT gateways
* Long-distance, noise-immune industrial communication
* Compact DIN-rail mount enclosure
* Easy configuration and integration into existing Modbus networks

### Typical Applications

* PLC I/O expansion
* Remote monitoring and control
* Factory automation
* Process automation
* Building management systems (BMS)
* Water and wastewater treatment
* Energy monitoring and control
* Industrial IoT and edge gateway applications

## Technical Specifications

| Parameter | Specification |
|-----------|---------------|
| **Communication Interface** | RS-485 |
| **Protocol** | Modbus RTU (Standard Modbus RTU Protocol) |
| **Supported Baud Rates** | 4800, 9600, 19200, 38400, 57600, 115200, 128000, 256000 bps |
| **Default Communication Settings** | 9600 bps, 8 Data Bits, No Parity, 1 Stop Bit (8-N-1) |
| **Power Supply** | 7–28 VDC |
| **Digital Inputs** | 8 Channels |
| **Input Voltage Range** | 5–24 VDC |
| **Input Type** | Supports Dry Contact, NPN (Sinking), and PNP (Sourcing) Inputs |
| **Input Isolation** | Built-in Bidirectional Optocoupler Isolation |
| **Digital Outputs** | 8 Channels |
| **Output Type** | Open-Drain (Low-Side Switching) |
| **Output Voltage Range** | 5–40 VDC |
| **Maximum Output Current** | 500 mA per Channel (Maximum) |
| **Modbus Slave Address** | Configurable from 1 to 255 |
| **Default Slave Address** | 1 (0x01) |

## Wiring

### Terminal Assignment

| Terminal | Description | Terminal | Description |
|----------|-------------|----------|-------------|
| **PWR IN** | Power Supply Positive (+) | **RS485+** | RS-485 Data A |
| **GND** | Power Supply Ground (-) | **RS485-** | RS-485 Data B |
| **NC** | Not Connected | **EARTH** | RS-485 Shield / Earth Ground |
| **DGND** | Signal Ground | **DGND** | Signal Ground |
| **DI7** | Digital Input Channel 8 | **DO7** | Digital Output Channel 8 |
| **DI6** | Digital Input Channel 7 | **DO6** | Digital Output Channel 7 |
| **DI5** | Digital Input Channel 6 | **DO5** | Digital Output Channel 6 |
| **DI4** | Digital Input Channel 5 | **DO4** | Digital Output Channel 5 |
| **DI3** | Digital Input Channel 4 | **DO3** | Digital Output Channel 4 |
| **DI2** | Digital Input Channel 3 | **DO2** | Digital Output Channel 3 |
| **DI1** | Digital Input Channel 2 | **DO1** | Digital Output Channel 2 |
| **DI0** | Digital Input Channel 1 | **DO0** | Digital Output Channel 1 |
| **DI COM** | Common Terminal for Digital Inputs | **DO COM** | Common Terminal for Digital Outputs |

---

### Digital Input Wiring

The IND-MOD-IO88 supports three types of digital input connections:

- **Dry Contact (Passive Input)**
- **NPN Sensor (Sinking Input)**
- **PNP Sensor (Sourcing Input)**

#### DI COM Configuration

The **DI COM** terminal determines how the digital inputs operate.

| DI COM Connection | Input Mode |
|-------------------|------------|
| Not Connected | Dry Contact (Passive) Input |
| Connected to **+V** | NPN (Low-Level Active) Input |
| Connected to **GND** | PNP (High-Level Active) Input |

!!! note

    The digital input voltage range is **5–24 VDC**.

---

<!-- #### Dry Contact (Passive) Input

Connect **DI COM** to **No Connection**. -->

<!-- ![Dry Contact Wiring](images/di_dry_contact.png) -->

<!-- ---

#### NPN Sensor Wiring

Connect **DI COM** to the **Positive Supply (+V)**. -->

<!-- ![NPN Wiring](images/di_npn.png) -->

<!-- ---

#### PNP Sensor Wiring

Connect **DI COM** to **GND**. -->

<!-- ![PNP Wiring](images/di_pnp.png) -->

<!-- --- -->

### Digital Output Wiring

The digital outputs are **Open-Drain (Low-Side Switching)** outputs.

Connect **DO COM** to the **positive terminal of the output power supply**.

The output load should be connected between **DO COM (+V)** and the corresponding **DOx** output.

!!! warning

    Each digital output can sink up to **500 mA maximum**.
    Exceeding this rating may permanently damage the output driver.

<!-- ![Digital Output Wiring](images/do_connection.png) -->

---

### RS-485 Wiring

| Terminal | Description |
|----------|-------------|
| **RS485+** | RS-485 Data A |
| **RS485-** | RS-485 Data B |
| **EARTH** | Cable Shield / Earth Ground (Recommended) |

!!! tip

    - Use twisted-pair cable for RS-485 communication.
    - Connect the cable shield to **EARTH** at one point only.
    - Terminate both ends of the RS-485 bus with **120 Ω** resistors when required.
    - Avoid running RS-485 cables alongside high-voltage or high-current wiring.

---

### Power Supply

| Terminal | Description |
|----------|-------------|
| **PWR IN** | Positive Supply (7-28V) |
| **GND** | Negative Supply |

!!! warning

    Verify the power supply polarity before powering the module. Reverse polarity may damage the device.