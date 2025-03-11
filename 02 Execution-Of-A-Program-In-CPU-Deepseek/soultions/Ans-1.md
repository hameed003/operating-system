Let's break down the execution of a simple C program that adds two numbers, step by step. We'll use the following example code:

```c
#include <stdio.h>

int main() {
    int a = 5;
    int b = 3;
    int sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```

---

### **1. Writing the C Program**

The code defines two integers (`a` and `b`), adds them, and prints the result using `printf`.

---

### **2. Preprocessing**

**What Happens**:  
The preprocessor handles directives starting with `#` (e.g., `#include`, `#define`).

- **Example**: `#include <stdio.h>` is replaced with the contents of the `stdio.h` header file (which declares `printf`).
- Macros (if any) are expanded.

**Simplified Preprocessed Output** (not actual code):

```c
// ... contents of stdio.h ...
int main() {
    int a = 5;
    int b = 3;
    int sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```

---

### **3. Compilation**

**What Happens**:  
The compiler (`gcc`/`clang`) converts preprocessed C code into **assembly language** (specific to the CPU architecture, e.g., x86 or ARM).

**Example Assembly Snippet** (x86):

```assembly
main:
    push    rbp
    mov     rbp, rsp
    mov     DWORD PTR [rbp-4], 5   ; a = 5
    mov     DWORD PTR [rbp-8], 3   ; b = 3
    mov     eax, DWORD PTR [rbp-4]
    add     eax, DWORD PTR [rbp-8] ; sum = a + b
    mov     DWORD PTR [rbp-12], eax
    mov     eax, DWORD PTR [rbp-12]
    mov     esi, eax
    lea     rdi, [rip+0x0]         ; "Sum: %d\n"
    mov     eax, 0
    call    printf
    mov     eax, 0
    pop     rbp
    ret
```

---

### **4. Assembly**

**What Happens**:  
The assembler converts assembly code into **machine code** (binary instructions) stored in an **object file** (`program.o`).

**Example Machine Code** (hexadecimal representation of `a + b`):

```
c7 45 fc 05 00 00 00   ; mov DWORD PTR [rbp-4], 5
c7 45 f8 03 00 00 00   ; mov DWORD PTR [rbp-8], 3
8b 45 fc                ; mov eax, DWORD PTR [rbp-4]
03 45 f8                ; add eax, DWORD PTR [rbp-8]
```

---

### **5. Linking**

**What Happens**:  
The linker (`ld`) combines object files and libraries (e.g., `libc.a` for `printf`) into an executable.

- Resolves external references (e.g., `printf` is linked to the C standard library).
- Creates the final executable (`a.out` or `program.exe`).

---

### **6. Loading**

**What Happens**:  
When you run `./a.out`, the operating system:

1. Allocates memory for the program.
2. Loads the executable into memory.
3. Sets up the stack (for local variables) and heap (for dynamic memory).
4. Transfers control to the program’s entry point (`_start`, which calls `main`).

---

### **7. Execution**

The CPU executes the machine instructions sequentially. Here's how the addition works at the hardware level:

#### **Step 1: Initialize Variables**

- The OS allocates space on the stack for `a`, `b`, and `sum`.
- `a` and `b` are stored in memory addresses (e.g., `0x7ffd4` and `0x7ffd8`).

#### **Step 2: Perform Addition**

1. **Fetch**: The CPU fetches the instruction `mov eax, DWORD PTR [rbp-4]` (load `a` into register `eax`).
2. **Decode**: The CPU decodes the instruction.
3. **Execute**: The Arithmetic Logic Unit (ALU) adds `a` and `b` (stored in registers).
   - `a` (5) → `eax` register.
   - `b` (3) → `ebx` register.
   - `add eax, ebx` → `eax` becomes 8.

#### **Step 3: Call `printf`**

- The `printf` function invokes a system call to write "Sum: 8" to the console.
- The OS handles the I/O operation.

#### **Step 4: Cleanup**

- The program returns `0` to the OS, indicating success.
- Memory is freed, and the process terminates.

---

### **Key Concepts**

1. **CPU Registers**: Small storage units (e.g., `eax`, `ebx`) for fast data access.
2. **ALU**: Performs arithmetic/logic operations (e.g., `a + b`).
3. **Stack**: Stores local variables and function call data.
4. **System Calls**: Interface between programs and the OS (e.g., `printf` uses `write`).

---

### **Visual Summary**

```
C Code → Preprocessing → Assembly → Machine Code → Linking → Executable → Loading → Execution (CPU/OS)
```

This entire process happens in milliseconds!
