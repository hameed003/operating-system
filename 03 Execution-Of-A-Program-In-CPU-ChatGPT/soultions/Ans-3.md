### **1. Program Counter (PC)**

#### **What is the Program Counter (PC)?**

The **Program Counter (PC)** is a special register inside the **CPU** that holds the **memory address of the next instruction** to be executed.

#### **Where is the Program Counter (PC) present?**

The **PC is part of the CPU’s control unit (CU)**. It plays a crucial role in the **Fetch-Decode-Execute cycle**.

#### **How does the PC work?**

- When an instruction is fetched from **RAM**, the **PC holds its address**.
- After execution, the PC is **incremented** to point to the next instruction.
- If a **jump, loop, or function call** occurs, the PC is updated to a different address.

#### **Example of PC in Action**

Consider this simple assembly code:

```assembly
MOV EAX, 5    ; PC = 1000h
ADD EAX, 7    ; PC = 1004h
MOV EBX, EAX  ; PC = 1008h
```

- Initially, the **PC points to 1000h** (where `MOV EAX, 5` is stored).
- After execution, it moves to **1004h** (next instruction).
- If a **function call or jump** happens, the PC is updated accordingly.

---

### **2. What are EAX and EBX?**

EAX and EBX are **CPU registers** in **x86 architecture**. Registers are **small storage locations inside the CPU** used for fast data access.

#### **What is EAX?**

- **EAX (Accumulator Register)**:
  - Used for **arithmetic and logic operations**.
  - Stores return values of functions.
  - Holds intermediate results.

#### **What is EBX?**

- **EBX (Base Register)**:
  - Used for **memory addressing** and **loop counters**.
  - Stores extra data during execution.

#### **Example Usage of EAX and EBX**

Let's say our C program has:

```c
int a = 5, b = 7, sum;
sum = a + b;
```

The assembly equivalent:

```assembly
MOV EAX, 5   ; Load 5 into EAX (a = 5)
MOV EBX, 7   ; Load 7 into EBX (b = 7)
ADD EAX, EBX ; Add EAX + EBX (5 + 7), store result in EAX
```

Now, **EAX holds 12**, which represents `sum = 12`.

---

### **Summary**

- **PC (Program Counter)** is inside the CPU's **Control Unit (CU)**, keeping track of instruction addresses.
- **EAX (Accumulator Register)** holds **arithmetic results** and **function return values**.
- **EBX (Base Register)** is used for **memory addressing and extra data storage**.

These components work together to **fetch, decode, and execute** instructions efficiently. Let me know if you need more details!
