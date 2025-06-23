# Elevate_Labs_Internship_Task_1
Elevate Labs Internship Task 1

# 🔍 Local Network Port Scanning & Traffic Analysis

This project was completed as part of my internship to learn how to discover open ports on devices in a local network and understand network exposure.

---

## 🧠 Objective

- Identify open ports on devices in the local network.
- Analyze network traffic generated during port scanning.
- Understand how attackers might discover vulnerable services.

---

## 🛠️ Tools Used

- **Nmap** – For scanning open ports.
- **Wireshark** – For capturing and analyzing packets.
- **Linux Terminal** – For command-line operations.

---

## 📊 Scanning Steps

1. TCP SYN Scan

    Command:
  
    nmap -sS <target-ip> -oN Port_scan
  
    Purpose: Performs a stealthy TCP SYN scan to identify open ports.

2. Open Ports Only

    Command:

    nmap --open -sS <target-ip> -oN Open_Port_Scan

    Purpose: Displays only open ports in the output.

3. Verbose Scan

    Command:

    nmap --open -sS -v <target-ip> -oN Open_Port_Scan(verbose)

    Purpose: Provides detailed output during scanning for better understanding.
   
---

## 📡 Packet Capture with Wireshark

  Ran Wireshark for approximately 60 seconds during scanning.

  Applied filters such as:

  tcp.flags.syn == 1

  Observed:

  - SYN packets sent to different ports.
  
  - SYN-ACK responses for open ports.

  - RST responses for closed ports.

  - Clear visibility of the scanning behavior.

---

## 📁 Files Included

  - Port_scan – Result of a basic TCP SYN scan.

  - Open_Port_Scan – Shows only open ports.

  - Open_Port_Scan(verbose) – Verbose output with detailed scanning steps.

  - (Optional) capture.pcapng – Packet capture file recorded during scan.

---

## 🔐 Conclusion

  - Open ports reveal running services and can be potential entry points.

  - Regular scanning helps in identifying unnecessary exposed services.

  - Monitoring and closing unused ports improves network security.

  - This exercise helped me understand how port scanning works on both tool and network levels.
