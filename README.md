# ICMP Data Exfiltration Tool

This is an **ICMP Data Exfiltration** tool designed to send and receive files over ICMP packets. It utilizes the `scapy` library for packet crafting and sends/receives data using ICMP echo requests and replies. The tool works by encoding data into ICMP packet payloads, which can be used for covert exfiltration of sensitive information over a network.

## Features

- **Send Files via ICMP**: Allows you to send files by encoding the file's data in ICMP packets.
- **Receive Files via ICMP**: Listen for incoming ICMP packets and reconstruct the original file.
- **Cross-Platform**: Works on both **Linux** and **Windows** platforms.
- **Admin Privileges Request**: Automatically requests admin privileges on Windows if necessary.
- **Progress Bar**: Displays a progress bar during the file transmission process.
- **Packet Filtering**: The script filters ICMP packets to avoid unnecessary noise and only capture relevant data.

## Prerequisites

1. **Python 3.x**: Make sure Python 3 is installed on your system.
2. **Scapy**: This tool uses the `scapy` library for packet crafting and manipulation.
   - Install it via pip:
     ```bash
     pip install scapy
     ```
3. **Colorama**: Used for colored terminal output.
   - Install it via pip:
     ```bash
     pip install colorama
     ```
4. **TQDM**: Provides a progress bar for the file transmission process.
   - Install it via pip:
     ```bash
     pip install tqdm
     ```
5. **Netifaces**: For network interface management.
   - Install it via pip:
     ```bash
     pip install netifaces
     ```

## Usage

### Arguments

- `-i <Interface/IP>`: Network interface name or IP address (e.g., `Ethernet` or `192.168.1.1`).
- `-m <Mode>`: Mode to use, either `send` or `recv`.
  - **send**: Send a file over ICMP packets.
  - **recv**: Receive a file over ICMP packets.
- `-f <Filename>`: The filename to send or receive.

### Example Commands

#### To send a file:

```bash
sudo python3 icmp_data_exfiltration.py -i "Ethernet" -m send -f testfile.txt
This will send the file testfile.txt over ICMP packets using the network interface Ethernet.

To receive a file:
bash
Copy
Edit
sudo python3 icmp_data_exfiltration.py -i "Ethernet" -m recv -f receivedfile.txt
This will listen for incoming ICMP packets and save the received data into the receivedfile.txt.

Requesting Admin Privileges on Windows
If running on Windows, the script will automatically request admin privileges (using UAC) when necessary. If you're not an administrator, the script will ask for permission to run with elevated rights.

Network Interfaces
To view the available network interfaces on your machine, use the following command:

Linux:

bash
Copy
Edit
ifconfig
Windows:

bash
Copy
Edit
ipconfig
File Transfer Progress
During the file transfer, the script will show a progress bar indicating the transmission status. After the file is sent, the script will output a success message.

Known Issues
The file transmission speed depends on the network latency and size of the file being transmitted.

Only works with IPv4 for the ICMP protocol.

Requires administrative privileges to send and receive ICMP packets on most systems.

Disclaimer
This tool is intended for ethical use only. It should only be used in environments where you have explicit permission to test network security. Unauthorized usage may be illegal in many jurisdictions.

License
This project is licensed under the MIT License - see the LICENSE file for details.


