### **Day 23: Mealy State Machine Design**  

#### **Concept Overview**  
A **Mealy State Machine** is a **Finite State Machine (FSM)** where the **output depends on both the current state and input**. This makes the Mealy machine more responsive since the output can change within a clock cycle instead of waiting for the next state transition.  

#### **Detailed Explanation**  
- **Components of a Mealy Machine:**  
  1. **States (Q):** Different conditions of the system.  
  2. **Inputs (X):** External signals affecting state transitions and outputs.  
  3. **State Transition Function (δ):** Defines next state based on inputs.  
  4. **Output Function (λ):** Output depends on both state and input.  
  5. **Clock:** Controls state transitions.  
  6. **Reset:** Initializes the FSM.  

- **Difference Between Moore and Mealy FSMs:**  
  - **Moore FSM:** Output depends only on the state.  
  - **Mealy FSM:** Output depends on both state and input, making it faster.  

#### **Example: 2-bit Sequence Detector (Detecting "10")**  
- **States Definition:**  
  - `S0`: Initial state (No bits detected)  
  - `S1`: '1' detected  
  - `S2`: '10' detected (output = 1 when input is 0)  

- **State Transition Table:**  

| Current State | Input (X) | Next State | Output (Z) |  
|--------------|----------|------------|------------|  
| S0          | 0        | S0         | 0          |  
| S0          | 1        | S1         | 0          |  
| S1          | 0        | S0         | 1          |  
| S1          | 1        | S1         | 0          |  

#### **State Diagram Representation**  
- **S0 → S1 on input 1**  
- **S1 → S0 with output 1 on input 0**  

#### **Boolean Expressions**  
- **Next State Logic:**  
  `S1 = S0 • X`  
  `S0 = S1 • X̅`  
- **Output Logic:**  
  `Z = S1 • X̅`  

#### **Applications**  
- Data transmission error detection  
- Digital counters  
- Pattern matching in digital circuits  

#### **Execution Steps**  
1. Open **QuestaSim/Xilinx ISE/Vivado**.  
2. Write the **Verilog code** for the Mealy FSM.  
3. Create a **testbench** to verify state transitions.  
4. Simulate and analyze the **waveform**.  

#### **Real-World Example for Practice**  
Design a **Mealy FSM for a traffic light controller** where the output (red, green, yellow) depends on both the current state and a sensor input.  

#### **Further Enhancements**  
- Modify the FSM to detect other sequences (e.g., "101").  
- Implement a **3-bit sequence detector** using a Mealy FSM.
