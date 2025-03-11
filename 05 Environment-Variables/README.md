## Youtube Links:

**Link1**: [Watch](https://www.youtube.com/watch?v=OnbpCg96w0I)
**Link2**: [Watch](https://www.youtube.com/watch?v=z84UIZy_qgE)
**Link3**: [Watch](https://www.youtube.com/watch?v=bd65z5VZ7L4)
**Link4**: [Watch](https://www.youtube.com/watch?v=ZqRQySWV9pM&feature=youtu.be)

**Environment variables** are a fundamental concept in operating systems like Windows, Linux, and macOS. They are used to store configuration settings, system paths, and other information that can be accessed by programs and scripts. Let’s dive into a detailed explanation of environment variables, including their purpose, usage, and examples across different operating systems.

---

## **1. What Are Environment Variables?**

- **Definition**: Environment variables are dynamic values that affect the behavior of processes and programs running on an operating system.
- **Purpose**: They provide a way to store and retrieve configuration settings, system paths, and other information that can be shared across multiple programs and scripts.
- **Scope**: Environment variables can be **system-wide** (available to all users and processes) or **user-specific** (available only to a specific user).

---

## **2. Common Uses of Environment Variables**

- **System Paths**: Store paths to executable files (e.g., `PATH`).
- **Configuration**: Store settings for applications (e.g., `JAVA_HOME`, `PYTHONPATH`).
- **Temporary Data**: Store temporary data for scripts or programs.
- **Customization**: Allow users to customize the behavior of the OS or applications.

---

## **3. Environment Variables in Different Operating Systems**

### **Windows**

#### **Viewing Environment Variables**

1. **Command Prompt**:

   - Use the `set` command to list all environment variables.
     ```cmd
     set
     ```
   - To view a specific variable, use:
     ```cmd
     echo %VARIABLE_NAME%
     ```
     Example:
     ```cmd
     echo %PATH%
     ```

2. **GUI**:
   - Right-click on **This PC** → **Properties** → **Advanced system settings** → **Environment Variables**.

#### **Setting Environment Variables**

1. **Temporary (for the current session)**:

   - Use the `set` command in the Command Prompt.
     ```cmd
     set MY_VAR=HelloWorld
     ```
   - Verify:
     ```cmd
     echo %MY_VAR%
     ```

2. **Permanent (system-wide or user-specific)**:
   - Use the **Environment Variables** GUI:
     - Add a new variable under **User variables** or **System variables**.

#### **Example: Setting `JAVA_HOME`**

1. Open the **Environment Variables** GUI.
2. Add a new variable:
   - **Variable name**: `JAVA_HOME`
   - **Variable value**: `C:\Program Files\Java\jdk-17`
3. Add `%JAVA_HOME%\bin` to the `PATH` variable.

---

### **Linux**

#### **Viewing Environment Variables**

1. **Terminal**:
   - Use the `printenv` command to list all environment variables.
     ```bash
     printenv
     ```
   - To view a specific variable, use:
     ```bash
     echo $VARIABLE_NAME
     ```
     Example:
     ```bash
     echo $PATH
     ```

#### **Setting Environment Variables**

1. **Temporary (for the current session)**:

   - Use the `export` command in the terminal.
     ```bash
     export MY_VAR="HelloWorld"
     ```
   - Verify:
     ```bash
     echo $MY_VAR
     ```

2. **Permanent (system-wide or user-specific)**:
   - Add the variable to a shell configuration file (e.g., `~/.bashrc`, `~/.bash_profile`, or `/etc/environment`).
     ```bash
     echo 'export MY_VAR="HelloWorld"' >> ~/.bashrc
     source ~/.bashrc
     ```

#### **Example: Setting `JAVA_HOME`**

1. Open the terminal.
2. Add the following to `~/.bashrc`:
   ```bash
   export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
   export PATH=$JAVA_HOME/bin:$PATH
   ```
3. Reload the configuration:
   ```bash
   source ~/.bashrc
   ```

---

### **macOS**

#### **Viewing Environment Variables**

1. **Terminal**:
   - Use the `printenv` command to list all environment variables.
     ```bash
     printenv
     ```
   - To view a specific variable, use:
     ```bash
     echo $VARIABLE_NAME
     ```
     Example:
     ```bash
     echo $PATH
     ```

#### **Setting Environment Variables**

1. **Temporary (for the current session)**:

   - Use the `export` command in the terminal.
     ```bash
     export MY_VAR="HelloWorld"
     ```
   - Verify:
     ```bash
     echo $MY_VAR
     ```

2. **Permanent (system-wide or user-specific)**:
   - Add the variable to a shell configuration file (e.g., `~/.bash_profile`, `~/.zshrc`, or `/etc/paths`).
     ```bash
     echo 'export MY_VAR="HelloWorld"' >> ~/.zshrc
     source ~/.zshrc
     ```

#### **Example: Setting `JAVA_HOME`**

1. Open the terminal.
2. Add the following to `~/.zshrc`:
   ```bash
   export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-17.jdk/Contents/Home
   export PATH=$JAVA_HOME/bin:$PATH
   ```
3. Reload the configuration:
   ```bash
   source ~/.zshrc
   ```

---

## **4. Common Environment Variables**

Here are some commonly used environment variables across operating systems:

| **Variable**   | **Purpose**                                               |
| -------------- | --------------------------------------------------------- |
| `PATH`         | Specifies directories where executable files are located. |
| `HOME`         | Specifies the current user’s home directory.              |
| `USER`         | Specifies the current username.                           |
| `SHELL`        | Specifies the current shell being used.                   |
| `JAVA_HOME`    | Specifies the location of the Java Development Kit (JDK). |
| `PYTHONPATH`   | Specifies additional directories for Python modules.      |
| `TEMP` / `TMP` | Specifies the directory for temporary files.              |

---

## **5. Best Practices for Using Environment Variables**

1. **Use Descriptive Names**: Choose meaningful names for custom variables (e.g., `API_KEY`, `DB_HOST`).
2. **Avoid Overwriting System Variables**: Be cautious when modifying system-wide variables like `PATH`.
3. **Secure Sensitive Data**: Avoid storing sensitive information (e.g., passwords) in environment variables. Use secure vaults or credential managers instead.
4. **Document Variables**: Document the purpose and usage of custom environment variables for future reference.

---

## **6. Example Use Cases**

### **Windows**

- **Setting `PATH`**:
  ```cmd
  set PATH=%PATH%;C:\MyProgram
  ```
- **Using `JAVA_HOME`**:
  ```cmd
  set JAVA_HOME=C:\Program Files\Java\jdk-17
  set PATH=%JAVA_HOME%\bin;%PATH%
  ```

### **Linux**

- **Setting `PATH`**:
  ```bash
  export PATH=$PATH:/usr/local/myprogram
  ```
- **Using `JAVA_HOME`**:
  ```bash
  export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
  export PATH=$JAVA_HOME/bin:$PATH
  ```

### **macOS**

- **Setting `PATH`**:
  ```bash
  export PATH=$PATH:/usr/local/myprogram
  ```
- **Using `JAVA_HOME`**:
  ```bash
  export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-17.jdk/Contents/Home
  export PATH=$JAVA_HOME/bin:$PATH
  ```

---

## **7. Summary**

- **Environment variables** are dynamic values used to configure the behavior of processes and programs.
- They can be **system-wide** or **user-specific**.
- **Windows**, **Linux**, and **macOS** all support environment variables, but the methods for setting and viewing them differ slightly.
- Common uses include setting system paths (`PATH`), configuring applications (`JAVA_HOME`), and storing temporary data.

By understanding and using environment variables effectively, you can customize your operating system and streamline the execution of programs and scripts.
