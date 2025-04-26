# Connect Kali Linux VM to TryHackMe using OpenVPN

## 🔶 How to Connect Kali Linux VM to TryHackMe using OpenVPN

### ✅ Step 1: Download Your OpenVPN (OVPN) Configuration File

Assuming you are currently using your Host machine, download your `OpenVPN (OVPN)` Configuration File from your `TryHackMe` account. 

**OpenVPN (Advanced) ➡️ Download**, as shown below.

![image](https://github.com/user-attachments/assets/8ed64f54-72f1-4ccc-87d7-1bf1ae5d2a6b)

This will download a `.ovpn` file (e.g., `username.ovpn`).

`Note:` You can reuse this file until it expires (they regenerate every 6 hours or so).

### ✅ Step 2: Enable Drag and Drop Between Host and Kali Linux VM

Now that you’ve downloaded your `OVPN` file onto your host machine, it is time to move it to your `Kali Linux VM` which can be done several ways (e.g., shared folders, drag-and-drop). In this case it’ll be via the `drag-and-drop` capability. 

**🔵 Install Guest Additions in Kali Linux VM**

`Guest Additions` is required for `drag-and-drop` to function. If you haven’t done this yet, run the following commands:

**🔹 *`sudo apt update`***

**🔹 *`sudo apt install -y build-essential dkms linux-headers-$(uname -r)`***

![image](https://github.com/user-attachments/assets/bf45535d-b9fb-46e5-b374-85934c1f167c)

**🔵 Enable Drag and Drop**

While the `Kali Linux VM` is running, from the top menu, go to: `Devices ➡️ Drag and Drop ➡️ Bidirectional` (for both directions), or `Host to Guest` (if you only want to drop files into the VM)

![image](https://github.com/user-attachments/assets/ac3682f3-c644-43ed-b2c6-ec24f9b19655)









