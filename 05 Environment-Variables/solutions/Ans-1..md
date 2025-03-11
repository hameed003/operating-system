### **Environment Variables in Operating Systems (Windows, Linux, macOS) – Detailed Explanation with Examples**

#### **What Are Environment Variables?**

Environment variables are **key-value pairs** stored in the operating system that provide important **configuration settings** for software and the OS itself. These variables define system paths, user preferences, and settings for applications, making them an essential part of system administration and development.

For example, when running a command in the terminal or command prompt, the system often checks the `PATH` environment variable to locate executable files.

---

## **1️⃣ Environment Variables in Windows**

### **Viewing Environment Variables**

To view system environment variables in Windows:

- Open **Command Prompt (cmd)** and type:

  ```sh
  set
  ```

  or

  ```sh
  echo %VAR_NAME%
  ```

  Example:

  ```sh
  echo %PATH%
  ```

  This prints the directories stored in the `PATH` variable.

- To view them in **GUI**:
  1. Right-click **This PC** → Click **Properties**
  2. Go to **Advanced system settings**
  3. Click **Environment Variables**

---

### **Common Windows Environment Variables**

| Variable        | Description                                                              |
| --------------- | ------------------------------------------------------------------------ |
| `%PATH%`        | Specifies directories where executable programs are located.             |
| `%USERPROFILE%` | Points to the current user’s home directory (e.g., `C:\Users\Username`). |
| `%TEMP%`        | Stores temporary files (`C:\Users\Username\AppData\Local\Temp`).         |
| `%SystemRoot%`  | Points to the Windows system directory (e.g., `C:\Windows`).             |
| `%USERNAME%`    | Shows the currently logged-in user.                                      |

### **Setting Environment Variables in Windows**

To set a temporary variable:

```sh
set MY_VAR=HelloWorld
```

To make it permanent (via **PowerShell**):

```powershell
[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "User")
```

To remove it:

```sh
set MY_VAR=
```

---

## **2️⃣ Environment Variables in Linux**

### **Viewing Environment Variables**

To list all environment variables:

```sh
printenv
```

or

```sh
env
```

To see a specific variable:

```sh
echo $HOME
```

---

### **Common Linux Environment Variables**

| Variable | Description                                                      |
| -------- | ---------------------------------------------------------------- |
| `$PATH`  | List of directories where executables are searched for commands. |
| `$HOME`  | User's home directory (e.g., `/home/username`).                  |
| `$USER`  | Currently logged-in user.                                        |
| `$SHELL` | The shell program being used (e.g., `/bin/bash`).                |
| `$PWD`   | Current working directory.                                       |

### **Setting Environment Variables in Linux**

To set a temporary variable (session-only):

```sh
export MY_VAR="HelloWorld"
```

To make it permanent, add it to **`~/.bashrc`** or **`~/.bash_profile`**:

```sh
echo 'export MY_VAR="HelloWorld"' >> ~/.bashrc
```

To remove a variable:

```sh
unset MY_VAR
```

---

## **3️⃣ Environment Variables in macOS**

Since macOS is Unix-based, it follows the same principles as Linux.

### **Viewing Environment Variables in macOS**

```sh
printenv
```

or

```sh
echo $SHELL
```

### **Common macOS Environment Variables**

| Variable | Description                                |
| -------- | ------------------------------------------ |
| `$PATH`  | Directories for executable programs.       |
| `$HOME`  | User’s home directory (`/Users/username`). |
| `$SHELL` | The shell in use (e.g., `/bin/zsh`).       |
| `$LANG`  | Language and localization settings.        |

### **Setting Environment Variables in macOS**

To set a temporary variable:

```sh
export MY_VAR="HelloMac"
```

To make it permanent, add it to **`~/.zshrc`** (for macOS Catalina and later):

```sh
echo 'export MY_VAR="HelloMac"' >> ~/.zshrc
```

Then reload the file:

```sh
source ~/.zshrc
```

To remove it:

```sh
unset MY_VAR
```

---

## **4️⃣ Differences Between Windows, Linux, and macOS**

| Feature                   | Windows                      | Linux                 | macOS                                |
| ------------------------- | ---------------------------- | --------------------- | ------------------------------------ |
| Variable Access Syntax    | `%VAR_NAME%`                 | `$VAR_NAME`           | `$VAR_NAME`                          |
| Permanent Storage         | Registry & System Properties | `.bashrc`, `.profile` | `.zshrc`, `.bash_profile`            |
| Command to View Variables | `set` or `echo %VAR_NAME%`   | `printenv` or `env`   | `printenv` or `env`                  |
| Default Shell             | `cmd.exe` or `PowerShell`    | `bash`/`zsh`          | `zsh` (default since macOS Catalina) |

---

## **5️⃣ Real-World Use Cases of Environment Variables**

1️⃣ **Configuring Software Paths**

- Adding Python to PATH in Windows:
  ```sh
  setx PATH "%PATH%;C:\Python39"
  ```

2️⃣ **Setting API Keys for Development**

- Instead of hardcoding API keys in a program, store them in environment variables:
  ```sh
  export API_KEY="your-secret-key"
  ```
  Then access it in Python:
  ```python
  import os
  api_key = os.getenv("API_KEY")
  ```

3️⃣ **Automating Tasks with Scripts**

- Using `$HOME` to create system-agnostic scripts:
  ```sh
  cp myfile.txt $HOME/Documents/
  ```

---

## **Conclusion**

- Environment variables **store important system-wide settings**.
- They help in **software configuration, scripting, and security**.
- Windows uses `%VAR_NAME%`, while Linux/macOS uses `$VAR_NAME`.
- They can be temporary or permanent based on how they are set.

Let me know if you need **specific examples** or a **detailed breakdown of any concept**! 🚀
