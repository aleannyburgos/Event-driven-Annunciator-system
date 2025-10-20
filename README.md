# ECE 495 – Event-Driven Circuit Design

This project implements an **event-driven annunciator system** using **EEPROM-based sequential logic**. It demonstrates hardware design techniques for programmable finite state machines without traditional random logic, focusing on modularity and reconfigurability.

---

## Overview

The circuit detects and signals alarm conditions based on simulated input events, mimicking industrial safety systems such as **gas pipeline pressure monitoring**.

---

## Implementation

### Components
- **AT28C64B EEPROM (8K x 8):** Stores state transitions and output data.
- **74LS374 Flip-Flop Register:** Buffers current state and synchronizes input signals.
- **Switches:** Represent inputs (TEST, LLA, HLA, ACK).
- **LEDs:** Represent system outputs (Green, Amber, Red – solid or flashing).

### System Inputs and Outputs
| Inputs | Description |
|--------|--------------|
| TEST | Manual test trigger |
| LLA | Low-level alarm (minor pressure drop) |
| HLA | High-level alarm (major pressure drop) |
| ACK | Acknowledge/reset condition |

| Outputs | Description |
|----------|--------------|
| Green | Normal state indicator |
| Amber | Low-level alarm indicator (solid or flashing) |
| Red | High-level alarm indicator (solid or flashing) |

---

## Design Methodology

1. **Draw the State Diagram**  
   - Include additional states (G, H) for flashing outputs.
2. **Assign State Variables**  
   - Based on student ID (e.g., `A=1, B=0, C=2, D=3, ...`).
3. **Create the Memory Table**  
   - Combine inputs and current state into EEPROM address bits.
   - Define next-state and output values as data bits.
4. **Program the EEPROM**  
   - Use **Batronix Programmer** and **Prog-Express software**.
   - Write hexadecimal data derived from the memory table.
5. **Hardware Assembly**  
   - Connect EEPROM, register, switches, and LEDs on a breadboard.
   - Verify state transitions and output behavior.

---

## Advantages

- **Programmable:** Easily update behavior by reprogramming EEPROM.  
- **Modular:** Simplifies circuit design by eliminating random logic gates.  
- **Error-tolerant:** Design corrections require only table edits.  

---

## Tools and Resources

- [Batronix Prog-Express Software](https://www.batronix.com/shop/software/prog-express/index.html)  
- [AT28C64B Datasheet (Atmel)](https://ww1.microchip.com/downloads/en/DeviceDoc/doc0270.pdf)  

---

## Deliverables

- State Diagram (with flashing states)  
- Memory Table in Excel  
- Connection Diagram  
- Picture of Programmed EEPROM and functioning circuit
- Video Demonstration

