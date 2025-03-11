In your scenario, where you have a **Linux machine** and a **Windows machine** on the **same network**, and you want to connect them using SSH, here’s how you can set up the **SSH client** and **SSH server**:

---

### **1. Define the Roles**

- **SSH Server**: The machine that will **accept incoming SSH connections**. This is the machine you want to control or access remotely.
- **SSH Client**: The machine that will **initiate the SSH connection** to the server. This is the machine you will use to control or access the server.

#### **In Your Case**:

- If you want to **control the Linux machine from the Windows machine**:
  - **SSH Server**: Linux machine.
  - **SSH Client**: Windows machine.
- If you want to **control the Windows machine from the Linux machine**:
  - **SSH Server**: Windows machine.
  - **SSH Client**: Linux machine.

---

### **2. Setting Up SSH Server and Client**

Let’s go through both scenarios in detail.

---

#### **Scenario 1: Linux as SSH Server, Windows as SSH Client**

##### **Step 1: Set Up SSH Server on Linux**

1. **Install OpenSSH Server**:

   - Open a terminal on the Linux machine and run:
     ```bash
     sudo apt update
     sudo apt install openssh-server
     ```

2. **Enable and Start SSH Service**:

   - Enable the SSH service to start automatically on boot:
     ```bash
     sudo systemctl enable ssh
     ```
   - Start the SSH service:
     ```bash
     sudo systemctl start ssh
     ```

3. **Check SSH Server Status**:

   - Verify that the SSH server is running:
     ```bash
     sudo systemctl status ssh
     ```

4. **Find the Linux Machine's IP Address**:
   - Run the following command to find the IP address:
     ```bash
     ip a
     ```
   - Look for the IP address under the network interface (e.g., `192.168.1.10`).

##### **Step 2: Set Up SSH Client on Windows**

1. **Install OpenSSH Client**:

   - Open **Settings** > **Apps** > **Optional Features**.
   - Click **Add a Feature** and install **OpenSSH Client**.

2. **Connect to the Linux Machine**:

   - Open **Command Prompt** or **PowerShell** on Windows.
   - Run the following command to connect to the Linux machine:
     ```bash
     ssh username@linux_ip_address
     ```
     Replace `username` with your Linux username and `linux_ip_address` with the Linux machine's IP address (e.g., `192.168.1.10`).

3. **Authenticate**:
   - Enter your Linux user's password when prompted.
   - If you’ve set up SSH keys, the connection will be authenticated automatically.

---

#### **Scenario 2: Windows as SSH Server, Linux as SSH Client**

##### **Step 1: Set Up SSH Server on Windows**

1. **Install OpenSSH Server**:

   - Open **Settings** > **Apps** > **Optional Features**.
   - Click **Add a Feature** and install **OpenSSH Server**.

2. **Enable and Start SSH Service**:

   - Open **PowerShell** as Administrator and run:
     ```bash
     Start-Service sshd
     Set-Service -Name sshd -StartupType Automatic
     ```

3. **Check SSH Server Status**:

   - Verify that the SSH server is running:
     ```bash
     Get-Service sshd
     ```

4. **Find the Windows Machine's IP Address**:
   - Open **Command Prompt** or **PowerShell** and run:
     ```bash
     ipconfig
     ```
   - Look for the IPv4 address under the network adapter (e.g., `192.168.1.20`).

##### **Step 2: Set Up SSH Client on Linux**

1. **Install OpenSSH Client (if not already installed)**:

   - Open a terminal on the Linux machine and run:
     ```bash
     sudo apt update
     sudo apt install openssh-client
     ```

2. **Connect to the Windows Machine**:

   - Run the following command to connect to the Windows machine:
     ```bash
     ssh username@windows_ip_address
     ```
     Replace `username` with your Windows username and `windows_ip_address` with the Windows machine's IP address (e.g., `192.168.1.20`).

3. **Authenticate**:
   - Enter your Windows user's password when prompted.
   - If you’ve set up SSH keys, the connection will be authenticated automatically.

---

### **3. Using SSH Keys for Authentication (Optional)**

To avoid entering passwords every time, you can set up **SSH key-based authentication**.

#### **Steps**:

1. **Generate SSH Keys on the Client**:

   - On the client machine (Linux or Windows), generate an SSH key pair:
     ```bash
     ssh-keygen -t ed25519 -C "your_email@example.com"
     ```
   - Save the key pair in the default location (`~/.ssh/id_ed25519`).

2. **Copy the Public Key to the Server**:

   - On the client machine, copy the public key to the server:
     ```bash
     ssh-copy-id username@server_ip_address
     ```
   - Enter the server's password when prompted.

3. **Test the Connection**:
   - Try connecting to the server again:
     ```bash
     ssh username@server_ip_address
     ```
   - You should no longer be prompted for a password.

---

### **4. Summary of Roles**

| **Scenario**                   | **SSH Server**  | **SSH Client**  |
| ------------------------------ | --------------- | --------------- |
| **Control Linux from Windows** | Linux machine   | Windows machine |
| **Control Windows from Linux** | Windows machine | Linux machine   |

---

### **5. Key Points**

- **SSH Server**: The machine you want to control remotely. You need to install and configure the SSH server software on this machine.
- **SSH Client**: The machine you use to connect to the SSH server. You need to install the SSH client software on this machine.
- **Authentication**: Use passwords or SSH keys for secure authentication.
- **Same Network**: Since both machines are on the same network, you don’t need to configure port forwarding or use public IP addresses.

---

Let me know if you need further assistance! 😊
