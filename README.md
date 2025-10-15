# Traffic-light-controller
This project implements a traffic light controller using Verilog HDL. The design uses a finite state machine (FSM) to manage traffic lights for four directions: North, South, East, and West. Each direction has Red, Yellow, and Green LEDs, and the FSM cycles through traffic phases with configurable durations for green and yellow lights.

The system simulates a real-world traffic intersection, ensuring safe transitions and only one direction has the green light at a time. This design is useful for learning digital design concepts, FSM implementation.


---

## Features
- FSM-based traffic light sequencing for four directions  
- Configurable timing for **Green and Yellow** lights   
- Reset functionality to start the sequence from **North Green**  
- Modular design for easy extension to more intersections or sensors  
- Suitable for **digital design learning**, **FPGA prototyping**, and **embedded systems projects**

---


## Traffic Light Sequence

The FSM cycles through the following sequence:

1. **North Green → North Yellow**  
2. **South Green → South Yellow**  
3. **East Green → East Yellow**  
4. **West Green → West Yellow**  

Each **green light** lasts for ~8 clock cycles (configurable in FSM), and **yellow light** lasts for ~4 clock cycles. Only one direction has green at a time; others are red or yellow during transition.


### LED Representation

| Direction | Green | Yellow | Red |
|-----------|-------|--------|-----|
| North     | ON/OFF| ON/OFF | ON/OFF |
| South     | ON/OFF| ON/OFF | ON/OFF |
| East      | ON/OFF| ON/OFF | ON/OFF |
| West      | ON/OFF| ON/OFF | ON/OFF |


---

## Learning Outcomes

- Implementing a **finite state machine (FSM)** in Verilog  
- Understanding **Digital Logic** and **Sequential Circuits**  
- Verilog Coding and Modeling Styles  
- Designing **modular and extendable digital circuits**  
- Timing, Counters,synthesis, Clock Division 

---

 
