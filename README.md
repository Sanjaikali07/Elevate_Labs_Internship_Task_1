
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

## ⚠️ Potential Security Risks from Open Ports

### 1. Host: 10.0.2.2

* **Port 135/tcp (msrpc)**

  * Microsoft RPC service has a history of critical vulnerabilities.
  * May allow remote code execution if not properly secured or updated.
  * Often targeted by malware for lateral movement.

* **Port 445/tcp (microsoft-ds)**

  * SMB protocol is a common target for ransomware (e.g., WannaCry).
  * May expose shared files and authentication credentials.
  * Vulnerable to brute-force, relay, and man-in-the-middle attacks.

### 2. Host: 10.0.2.3

* **Port 53/tcp (domain)**

  * If misconfigured, DNS service can allow unauthorized zone transfers.
  * May be leveraged for DNS amplification or cache poisoning attacks.
  * Can reveal internal network structure to attackers.

### 🔐 General Risks

* Open ports indicate active services that expand the attack surface.
* Unmonitored or outdated services are highly vulnerable to exploitation.
* Attackers may use port scanning as the first step to identify weaknesses in the network.

---

## 📡 Packet Capture with Wireshark

  Ran Wireshark for approximately 60 seconds during scanning.

---

## 📁 Files Included

  - Port_scan.txt – Result of a basic TCP SYN scan.

  - Open_Port_Scan.txt – Shows only open ports.

  - Open_Port_Scan(verbose).txt – Verbose output with detailed scanning steps.

  - Packets captured.pcapng – Packet capture file recorded during scan.

---

## 🔐 Conclusion

  - Open ports reveal running services and can be potential entry points.

  - Regular scanning helps in identifying unnecessary exposed services.

  - Monitoring and closing unused ports improves network security.

  - This exercise helped me understand how port scanning works on both tool and network levels.

---

## 👨‍💻 Author

Sanjai K

Aspiring Penetration Tester
