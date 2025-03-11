### **How the Program Counter (PC) Works in Instruction Execution**

The **Program Counter (PC)** plays a key role in the **Fetch-Decode-Execute Cycle**. It helps the **Control Unit (CU)** fetch instructions from the **Memory Unit (MU)** and execute them step by step.

---

## **1. Program Counter's Role in the CPU**

The **Program Counter (PC)** is a **special register inside the Control Unit (CU)** that stores the **address of the next instruction** to be executed.

### **Where is the Program Counter?**

- The **PC is inside the CPU's Control Unit (CU)**.
- It is **not in the Memory Unit (MU)** but works closely with it.

### **How the PC Works with the Control Unit (CU)?**

1. The **PC holds the memory address** of the next instruction.
2. The **Control Unit (CU) reads the PC's value** and sends it to the **Memory Unit (MU)**.
3. The **Memory Unit (MU) fetches** the instruction from RAM and sends it to the **Instruction Register (IR)** inside the **CU**.
4. The **PC is updated** to point to the next instruction.

---

## **2. Step-by-Step Execution with the PC**

Let's assume we have a simple program:

```assembly
MOV EAX, 5   ; Load 5 into EAX
ADD EAX, 7   ; Add 7 to EAX
MOV EBX, EAX ; Store result in EBX
```

### **Step 1: Fetch (Using PC and MU)**

- Initially, **PC = 1000h** (assume the instruction `MOV EAX, 5` is stored at this address in RAM).
- The **CU sends 1000h to the MU**.
- The **MU fetches the instruction** stored at 1000h and places it in the **Instruction Register (IR)**.
- The **PC is incremented to 1004h** (points to the next instruction).

**Now:**

```
PC = 1004h  (Ready for next instruction)
IR = MOV EAX, 5  (Fetched instruction)
```

---

### **Step 2: Decode (Control Unit)**

- The **CU reads the IR (MOV EAX, 5)**.
- It **identifies the operation** as "Move 5 to the EAX register".
- The **CU signals the ALU** to execute the instruction.

---

### **Step 3: Execute (ALU and Registers)**

- The **ALU moves 5 into EAX**.
- The **CU updates the PC** to **1004h**, where the next instruction (`ADD EAX, 7`) is stored.

Now, **repeat steps for the next instruction**:

- The **CU fetches `ADD EAX, 7`** from RAM (address **1004h**).
- The **PC updates to 1008h** (next instruction address).
- The **CU decodes and tells ALU to add 7 to EAX**.
- **EAX now holds 12**.

---

### **3. How PC Works with Loops and Jumps**

If a **jump or function call** happens:

- The **PC updates to a different memory address** instead of incrementing sequentially.

Example (Loop):

```assembly
START:
  ADD EAX, 1   ; Increase EAX by 1
  CMP EAX, 10  ; Compare EAX with 10
  JNE START    ; If not equal, jump back to START
```

- If `EAX != 10`, **PC updates back to START**.
- If `EAX == 10`, the **PC moves to the next instruction**.

---

## **Final Summary**

1. **PC stores the address of the next instruction** and is part of the **Control Unit (CU)**.
2. **CU reads the PC and tells the Memory Unit (MU) to fetch the instruction** from RAM.
3. **PC updates** after each instruction (or jumps to a different location for loops/functions).
4. **CU decodes and instructs the ALU to execute operations**.

The **Program Counter (PC) is the key to sequential execution in the CPU**. Let me know if you need further clarification!
