# SSH & Other Ways To Take Remote Access Of A Machine:

Taking remote access of a friend's system who is connected to a different network can be achieved using various methods, depending on the operating systems, tools, and level of access required. Below, I’ll explain the most common and secure ways to achieve this, along with step-by-step examples.

---

### **1. Using Remote Desktop Software**

Remote desktop software allows you to control another computer over the internet. Here are some popular tools:

---

#### **a. AnyDesk**

**Steps**:

1. **Install AnyDesk**:

   - Both you and your friend download and install AnyDesk from [anydesk.com](https://anydesk.com).

2. **Share the AnyDesk Address**:

   - Your friend opens AnyDesk and shares their **AnyDesk address** (a 9-digit number) with you.

3. **Connect**:

   - Enter your friend's AnyDesk address in your AnyDesk application and click **Connect**.
   - Your friend will receive a connection request and must approve it.

4. **Control the Remote System**:
   - Once connected, you can control your friend's system remotely.

---

#### **b. TeamViewer**

**Steps**:

1. **Install TeamViewer**:

   - Both you and your friend download and install TeamViewer from [teamviewer.com](https://teamviewer.com).

2. **Share the TeamViewer ID and Password**:

   - Your friend opens TeamViewer and shares their **TeamViewer ID** and **temporary password** with you.

3. **Connect**:

   - Enter your friend's TeamViewer ID in your TeamViewer application and click **Connect**.
   - Enter the temporary password when prompted.

4. **Control the Remote System**:
   - Once connected, you can control your friend's system remotely.

---

### **2. Using Built-In Remote Access Tools**

Most operating systems have built-in tools for remote access.

---

#### **a. Windows Remote Desktop (RDP)**

**Steps**:

1. **Enable Remote Desktop on Your Friend's System**:

   - On your friend's Windows system:
     - Go to **Settings** > **System** > **Remote Desktop**.
     - Turn on **Enable Remote Desktop**.

2. **Find the IP Address**:

   - Your friend needs to share their **public IP address** (you can find it by searching "What is my IP" on Google).

3. **Configure Port Forwarding (if behind a router)**:

   - Your friend needs to configure their router to forward **port 3389** (default RDP port) to their system's local IP address.

4. **Connect Using Remote Desktop Connection**:
   - On your system:
     - Open the **Remote Desktop Connection** app.
     - Enter your friend's public IP address and click **Connect**.
     - Enter your friend's username and password when prompted.

---

#### **b. macOS Screen Sharing**

**Steps**:

1. **Enable Screen Sharing on Your Friend's Mac**:

   - On your friend's Mac:
     - Go to **System Preferences** > **Sharing**.
     - Enable **Screen Sharing**.

2. **Find the IP Address**:

   - Your friend needs to share their **public IP address**.

3. **Configure Port Forwarding (if behind a router)**:

   - Your friend needs to forward **port 5900** (VNC port) to their Mac's local IP address.

4. **Connect Using a VNC Client**:
   - On your system:
     - Use a VNC client (e.g., RealVNC, TightVNC).
     - Enter your friend's public IP address and connect.
     - Enter your friend's username and password when prompted.

---

### **3. Using SSH (for Command-Line Access)**

If you only need command-line access, SSH is a secure and lightweight option.

---

#### **Steps**:

1. **Enable SSH on Your Friend's System**:

   - On Linux/macOS:
     - Open a terminal and run:
       ```bash
       sudo systemctl enable ssh
       sudo systemctl start ssh
       ```
   - On Windows:
     - Enable the **OpenSSH Server** feature:
       - Go to **Settings** > **Apps** > **Optional Features** > **Add a Feature** > **OpenSSH Server**.

2. **Find the IP Address**:

   - Your friend needs to share their **public IP address**.

3. **Configure Port Forwarding (if behind a router)**:

   - Your friend needs to forward **port 22** (default SSH port) to their system's local IP address.

4. **Connect Using SSH**:
   - On your system:
     - Open a terminal and run:
       ```bash
       ssh username@friend_public_ip
       ```
     - Enter your friend's password when prompted.

---

### **4. Using VPN for Secure Access**

A VPN (Virtual Private Network) can create a secure tunnel between your system and your friend's network, allowing you to access their system as if you were on the same local network.

---

#### **Steps**:

1. **Set Up a VPN Server**:

   - Your friend sets up a VPN server on their router or system (e.g., using OpenVPN or WireGuard).

2. **Connect to the VPN**:

   - You install the VPN client and connect to your friend's VPN server using the credentials they provide.

3. **Access the Remote System**:
   - Once connected to the VPN, you can use tools like RDP, SSH, or VNC to access your friend's system.

---

### **5. Using Cloud-Based Remote Access Tools**

Some tools allow remote access without requiring port forwarding or public IP addresses.

---

#### **a. Chrome Remote Desktop**

**Steps**:

1. **Install Chrome Remote Desktop**:

   - Both you and your friend install the Chrome Remote Desktop extension from the Chrome Web Store.

2. **Set Up Remote Access**:

   - Your friend sets up remote access by following the instructions in the Chrome Remote Desktop app.

3. **Share the Access Code**:

   - Your friend shares the **access code** with you.

4. **Connect**:
   - Enter the access code in your Chrome Remote Desktop app to connect.

---

#### **b. Remote Utilities**

**Steps**:

1. **Install Remote Utilities**:

   - Both you and your friend download and install Remote Utilities from [remoteutilities.com](https://remoteutilities.com).

2. **Set Up the Host**:

   - Your friend installs the **Host** component and shares their **ID** and **password** with you.

3. **Connect**:
   - You install the **Viewer** component and enter your friend's ID and password to connect.

---

### **6. Security Considerations**

- **Use Strong Passwords**: Ensure both systems use strong, unique passwords.
- **Enable Encryption**: Use tools that support encryption (e.g., SSH, VPN, RDP).
- **Limit Access**: Only allow remote access when necessary and disable it afterward.
- **Use Trusted Tools**: Stick to well-known, reputable remote access tools.

---

### **Summary of Methods**

| **Method**                | **Ease of Use** | **Security** | **Use Case**                         |
| ------------------------- | --------------- | ------------ | ------------------------------------ |
| **AnyDesk/TeamViewer**    | Easy            | High         | Quick, cross-platform remote access. |
| **Windows RDP**           | Moderate        | High         | Full control of Windows systems.     |
| **macOS Screen Sharing**  | Moderate        | High         | Full control of macOS systems.       |
| **SSH**                   | Moderate        | High         | Command-line access for Linux/macOS. |
| **VPN + RDP/SSH**         | Advanced        | Very High    | Secure access to local network.      |
| **Chrome Remote Desktop** | Easy            | High         | Browser-based remote access.         |
| **Remote Utilities**      | Easy            | High         | Lightweight remote access tool.      |

---

Choose the method that best fits your needs and technical expertise. Let me know if you need further assistance! 😊
