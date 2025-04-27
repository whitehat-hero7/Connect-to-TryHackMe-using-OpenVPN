# Connect Kali Linux VM to TryHackMe using OpenVPN

## 🔶 How to Connect Kali Linux VM to TryHackMe using OpenVPN

`OpenVPN` is an open-source software application that creates secure, encrypted connections over the internet, known as a `Virtual Private Network (VPN)`. It allows users to secure their network traffic, access remote networks safely, and mask their real IP addresses by routing traffic through a `VPN` server. `OpenVPN` works by using encryption protocols like `SSL/TLS` to establish a secure tunnel between a user's device and a remote server, typically configured through a provided `.ovpn` file. Once connected, all data travels through this encrypted tunnel, protecting it from hackers and eavesdroppers. In environments like `TryHackMe`, `OpenVPN` is essential for securely connecting a local machine, such as a `Kali Linux VM`, to a private network of virtual machines, enabling users to interact with and attack targets within a safe and isolated environment.

### ✅ Step 1: Download Your OpenVPN (OVPN) Configuration File

Download your `OpenVPN (OVPN)` Configuration File from your `TryHackMe` account. 

**OpenVPN (Advanced) ➡️ Download**, as shown below.

![image](https://github.com/user-attachments/assets/8ed64f54-72f1-4ccc-87d7-1bf1ae5d2a6b)

This will download a `.ovpn` file (e.g., `username.ovpn`).

`Note:` You can reuse this file until it expires (they regenerate every 6 hours or so).

### ✅ Step 2: Enable Drag and Drop Between Host and Kali Linux VM

Now that you’ve downloaded your `OVPN` file, assuming you are in your host machine, it is time to move it to your `Kali Linux VM` which can be done several ways (e.g., shared folders, drag-and-drop). In this case it’ll be via the `drag-and-drop` capability. 

**🔵 Install Guest Additions in Kali Linux VM**

`Guest Additions` is required for `drag-and-drop` to function. If you haven’t done this yet, run the following commands:

**🔹 *`sudo apt update`***

**🔹 *`sudo apt install -y build-essential dkms linux-headers-$(uname -r)`***

![image](https://github.com/user-attachments/assets/bf45535d-b9fb-46e5-b374-85934c1f167c)

**🔵 Enable Drag and Drop**

While the `Kali Linux VM` is running, from the top menu, go to: `Devices ➡️ Drag and Drop ➡️ Bidirectional` (for both directions), or `Host to Guest` (if you only want to drop files into the VM)

![image](https://github.com/user-attachments/assets/ac3682f3-c644-43ed-b2c6-ec24f9b19655)

### ✅ Step 3: Use Drag and Drop

After everything is set:

To avoid `drag-and-drop` errors, simply drag a file from your host into the `Kali Linux VM` Desktop window (or vice versa) as shown below. Files are usually dropped into the Desktop or Home folder in `Kali Linux VM`.

![image](https://github.com/user-attachments/assets/1e4e650e-5d6a-42e8-a8a2-fa192822f046)

### ✅ Step 4: Connect to TryHackMe’s Network using OpenVPN

**🔵 Make sure OpenVPN is installed in Kali Linux VM**

**🔹 *`sudo apt update`***

**🔹 *`sudo apt install openvpn -y`***

![image](https://github.com/user-attachments/assets/3aa12f65-d4e1-4f1a-a25a-2a6dc703b23f)

**🔵 Connect to OpenVPN**

**🔹 *`sudo openvpn <your_username.ovpn>`***

`Note:` Verify you are in the directory where your `.ovpn` file is located or you are using the full file path (e.g., `/home/whitehathero/Desktop/Whitehathero.ovpn`) when running the command.

![image](https://github.com/user-attachments/assets/662fb01e-bf9f-45ed-be4c-bd3ecd979cdf)

If ran correctly, you should see the `“Initialization Sequence Completed”` message as shown below, meaning that you’ve successfully connected!

![image](https://github.com/user-attachments/assets/5f29b2e0-4253-454e-a38c-28e852e7d83f)

Your `Kali Linux VM` is now part of the `TryHackMe` network — you can start pinging and attacking target machines using the IPs listed in a room (usually in the 10.10.x.x range). 

🛑 If for any reason you can’t connect using your `.ovpn` file, re-download your `.ovpn` file from `TryHackMe` and start the connection process again. 

To avoid connection issues, you’ll need to keep the terminal window running `OpenVPN` active while you interact with a target machine. If you want to disconnect, press `Ctrl + C`.

**🔵 Verify connection to TryHackMe**

**🔹 *`ip a`***

You should see an interface named `tun0` and your assigned `OpenVPN` IP address, as shown below.

![image](https://github.com/user-attachments/assets/aac5250f-dd5b-406e-94a9-57e236ed0938)

**🔹 *`ping -c 4 10.10.10.10`***

If you can successfully ping `10.10.10.10` as shown below with `0% packet loss`, then you are connected to `TryHackMe`, also allowing you to ping the provided `Target IP Address`.

![image](https://github.com/user-attachments/assets/19dd658b-6085-4eb2-81e1-680e7c020a1c)

🎉 Congratulations! You’re now successfully connected to the `TryHackMe` network using `OpenVPN`. This allows you to participate in challenges and labs directly from your own `Kali Linux VM` attack machine, using the `Target IP addresses` provided in each room.

By connecting this way, you're no longer limited by the time constraints of the `TryHackMe AttackBox`. You gain full flexibility to complete tasks, explore environments, and build your skills at your own pace — all while using your own setup.












