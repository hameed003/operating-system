Yes! In this scenario, **only one logical core will be used** because there is only **one process with one main thread running**.

### **🔹 Explanation:**

- Your system has **4 physical cores and 8 logical cores** (which means Hyper-Threading is enabled).
- If **no other process is running**, and you start a **single-threaded program**, the operating system (OS) will assign this **one thread to one logical core**.
- The remaining **7 logical cores will be idle** unless another process or thread starts running.

---

### **🔹 How CPU Scheduling Works in This Case:**

- The **OS scheduler** decides which **logical core** to assign the process to.
- Since your program has only **one main thread**, it doesn’t need multiple cores.
- So, the **OS picks one available logical core** and executes the thread on it.

---

### **🔹 What Happens If You Run More Threads?**

✅ If your program starts **multiple threads**, the OS can distribute them across **multiple logical cores**.  
✅ If the program is **multi-threaded**, it can take advantage of the **8 logical cores** to run faster.

---

### **🔹 Final Answer:**

✅ **Yes, only one logical core will be used if your program has only one main thread.**  
✅ The remaining **7 logical cores** will stay idle until more threads or programs run.

Would you like an example to test this on your system? 😊
