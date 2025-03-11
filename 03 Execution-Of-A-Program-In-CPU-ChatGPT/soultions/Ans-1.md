When you execute a C program, it goes through multiple stages before producing the final output. Below is a detailed step-by-step explanation of how a simple C program runs on a machine.

---

## **Step 1: Writing the C Code**

We start with writing a simple C program to add two numbers.

```c
#include <stdio.h>

int main() {
    int a = 5, b = 7, sum;
    sum = a + b;
    printf("Sum = %d\n", sum);
    return 0;
}
```

---

## **Step 2: Preprocessing**

Before compilation, the **preprocessor** handles directives like `#include <stdio.h>`. It performs tasks such as:

1. Expanding macros.
2. Including header files.
3. Removing comments.

### **Example of Preprocessed Code**

After preprocessing, the code will expand to include the contents of `stdio.h` in place of `#include <stdio.h>`, removing unnecessary comments.

---

## **Step 3: Compilation**

After preprocessing, the **compiler** (like `gcc`) translates the code into **assembly language**.

#### **Example Assembly Output**

The compiler converts the C code into low-level assembly instructions.

```assembly
mov eax, 5   ; Load 5 into register eax
add eax, 7   ; Add 7 to eax
```

---

## **Step 4: Assembly**

The assembler (`as`) converts the assembly code into **machine code (binary form)**, producing an **object file** (`.o` file).

```bash
gcc -c add.c -o add.o
```

At this stage, `add.o` contains machine code, but it is not yet executable.

---

## **Step 5: Linking**

The linker (`ld`) links the object file with necessary system libraries (like `stdio.h` functions) to create an executable (`a.out`).

```bash
gcc add.o -o add
```

This step ensures all function calls (like `printf`) are correctly mapped.

---

## **Step 6: Loading**

When we execute the program (`./add`), the **Operating System (OS)** loads the executable into **RAM**.

- The OS **allocates memory** for:
  - Code
  - Data
  - Stack (for function calls)
  - Heap (for dynamic memory)

---

## **Step 7: Execution by CPU**

The **CPU fetches** machine instructions and executes them step by step.

**Example Execution Steps:**

1. Load `a = 5` into a register.
2. Load `b = 7` into another register.
3. Perform addition (`sum = a + b`).
4. Call `printf` to print the output.

---

## **Step 8: Output Display**

Finally, the output appears on the terminal.

```bash
Sum = 12
```

---

### **Summary of Execution Steps**

| Step | Process                                                     |
| ---- | ----------------------------------------------------------- |
| 1    | **Preprocessing** (`#include` expansion, removing comments) |
| 2    | **Compilation** (C → Assembly)                              |
| 3    | **Assembly** (Assembly → Machine Code)                      |
| 4    | **Linking** (Combining object files and libraries)          |
| 5    | **Loading** (OS loads executable into RAM)                  |
| 6    | **Execution** (CPU runs instructions)                       |
| 7    | **Output** (Result is displayed)                            |

Let me know if you want a deeper explanation of any step!
