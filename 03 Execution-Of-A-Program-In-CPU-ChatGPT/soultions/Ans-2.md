Once our C program is loaded into RAM, the **CPU (Central Processing Unit)** takes control and executes it step by step. The CPU consists of three main components:

1. **Memory Unit (MU)** – Fetches instructions and data from RAM.
2. **Control Unit (CU)** – Directs and manages the execution of instructions.
3. **Arithmetic and Logic Unit (ALU)** – Performs calculations and logical operations.

Let’s go deep into each stage of execution:

---

## **1. Loading into RAM**

When you run `./add`, the **Operating System (OS)** loads the executable file into **RAM**. The program is stored in different memory sections:

| Section          | Purpose                                                         |
| ---------------- | --------------------------------------------------------------- |
| **Code Section** | Stores the machine instructions of the program.                 |
| **Data Section** | Stores global and static variables.                             |
| **Stack**        | Stores function calls, local variables, and return addresses.   |
| **Heap**         | Stores dynamically allocated memory (not used in this example). |

Example memory layout:

```
---------------------------------
|  Code Section  (Executable)   |
---------------------------------
|  Data Section  (Global vars)  |
---------------------------------
|        Stack (Grows Down)     |
---------------------------------
|        Heap  (Grows Up)       |
---------------------------------
```

The **Program Counter (PC)** is set to the first instruction.

---

## **2. Instruction Execution Cycle**

Each instruction follows the **Fetch-Decode-Execute Cycle** inside the CPU.

### **Step 1: Fetch (Memory Unit & Control Unit)**

- The **Memory Unit (MU)** fetches the instruction from RAM using the **Program Counter (PC)**.
- The instruction is stored in the **Instruction Register (IR)**.

Example: Fetching `mov eax, 5`

```
PC -> 1000h (Address of instruction)
MU fetches instruction from 1000h
IR <- "mov eax, 5"
PC = PC + 1 (Points to next instruction)
```

---

### **Step 2: Decode (Control Unit)**

- The **Control Unit (CU)** reads the instruction and identifies the operation.
- It prepares the necessary CPU components to execute the instruction.

Example: Decoding `mov eax, 5`

```
CU reads "mov eax, 5"
CU identifies "mov" as a data transfer instruction
CU signals ALU to move 5 into register eax
```

---

### **Step 3: Execute (ALU)**

- If the instruction is an arithmetic operation, the **Arithmetic and Logic Unit (ALU)** processes it.

Example: Executing `add eax, 7`

```
ALU: 5 + 7 = 12
Result stored in eax register
```

---

## **3. Breaking Down Execution of Our C Program**

Let’s analyze how the CPU processes the key lines:

### **Step 1: Load Values into Registers**

For `int a = 5, b = 7;`

```
mov eax, 5   ; Store 5 in register eax
mov ebx, 7   ; Store 7 in register ebx
```

- **MU** fetches `mov eax, 5` and `mov ebx, 7` from RAM.
- **CU** decodes the instructions.
- **ALU** moves 5 into `eax` and 7 into `ebx`.

---

### **Step 2: Perform Addition**

For `sum = a + b;`

```
add eax, ebx  ; eax = eax + ebx (5 + 7 = 12)
```

- **CU** recognizes `add` instruction.
- **ALU** performs the addition: `5 + 7 = 12`.
- **eax** now holds `12`.

---

### **Step 3: Print Output**

For `printf("Sum = %d\n", sum);`

```
push eax      ; Push sum (12) onto the stack
call printf   ; Call printf function
```

- The **Stack** stores the value `12` as an argument.
- **CU** calls the `printf` function, which interacts with RAM and output devices.
- The **OS Kernel** prints `"Sum = 12"` on the terminal.

---

## **4. Storing and Retrieving Data**

- The **Memory Unit (MU)** ensures data is stored in RAM registers.
- The **Control Unit (CU)** manages data flow between registers and the ALU.
- The **ALU** performs operations on these values.

---

## **5. Completion and Exit**

- After executing `return 0;`, the **CU** signals the OS that the program is complete.
- The OS **clears the allocated memory** and frees resources.

---

## **Final Summary**

1. **RAM loads program sections** (Code, Stack, Data).
2. **CPU Fetches instructions** (MU fetches from RAM → PC updates).
3. **Control Unit Decodes** instructions.
4. **ALU Executes** calculations.
5. **Stack Handles function calls** (printf, return values).
6. **Program Ends**, OS cleans memory.

This is how a program actually runs inside your computer! Let me know if you need deeper details.
