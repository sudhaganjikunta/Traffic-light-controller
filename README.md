# Traffic-light-controller
This project implements a traffic light controller using Verilog HDL. The design uses a finite state machine (FSM) to manage traffic lights for four directions: North, South, East, and West. Each direction has Red, Yellow, and Green LEDs, and the FSM cycles through traffic phases with configurable durations for green and yellow lights.

The system simulates a real-world traffic intersection, ensuring safe transitions and only one direction has the green light at a time. This design is useful for learning digital design concepts, FSM implementation.


---

## Features
- FSM-based traffic light sequencing for four directions  
- Configurable timing for **Green and Yellow** lights  
- **Clock divider** to convert FPGA high-speed clock to human-observable timing (~1Hz)  
- Reset functionality to start the sequence from **North Green**  
- Modular design for easy extension to more intersections or sensors  
- Suitable for **digital design learning**, **FPGA prototyping**, and **embedded systems projects**

---

## Project Structure

| File | Description |
|------|-------------|
| `traffic_control.v` | FSM module controlling traffic light states |
| `top_traffic_control.v` | Top module with clock divider and FPGA pin mapping |
| `clock_divider.v` | Generates slow clock from FPGA 100 MHz clock |
| `constraints.xdc` | Pin mapping for LEDs and reset button on Nexys A7 |

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

*(Add FPGA board photos or simulation screenshots here for visual demonstration)*

---

## FPGA Implementation Steps

1. Open **Vivado** and create a new RTL project.  
2. Add the Verilog source files (`traffic_control.v`, `top_traffic_control.v`, `clock_divider.v`).  
3. Add `.xdc` constraints file and map **LEDs and reset button**.  
4. Run **Synthesis → Implementation → Generate Bitstream**.  
5. Connect **Nexys A7** via USB and open **Hardware Manager**.  
6. Program the FPGA with the `.bit` file.  
7. Observe the traffic light sequence on LEDs.  

---

## Testing Instructions

1. Observe LEDs representing each traffic light:  
   - **Green** → Go  
   - **Yellow** → Wait  
   - **Red** → Stop  
2. Verify the **sequence** follows: North → South → East → West.  
3. Press the **reset button** to restart from **North Green**.  
4. Ensure LEDs light up according to FSM timing for **green** and **yellow** phases.  

---

## Learning Outcomes

- Implementing a **finite state machine (FSM)** in Verilog  
- Understanding **clock division** for timing control in FPGA  
- Mapping **digital outputs** to LEDs on FPGA board  
- Designing **modular and extendable digital circuits**  
- Debugging and testing **FPGA-based designs using Vivado**  

---

 
