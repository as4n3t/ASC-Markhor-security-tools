# 🛡️ ASC MARKHOR | Cybersecurity Tools

A collection of basic cybersecurity utilities and learning tools developed for ethical security practice, reconnaissance understanding, and network fundamentals.

---

## ⚙️ Tool: Basic Port Scanner (Python)

This script performs a simple TCP port scan to identify open ports and running services on a target system.

### 📌 Features

* IP / Hostname scanning
* Port range: 1 - 1024
* Service detection (if available)
* Lightweight and fast execution
* Educational use for network security basics

---

### 💻 Code

```python
import socket

target = input("Target IP or Hostname: ")

print(f"\nScanning {target}...\n")

for port in range(1, 1025):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(0.5)

        result = sock.connect_ex((target, port))

        if result == 0:
            try:
                service = socket.getservbyport(port)
            except:
                service = "Unknown"

            print(f"[OPEN] Port {port} ({service})")

        sock.close()

    except KeyboardInterrupt:
        print("\nScan stopped.")
        break

    except:
        pass
```

---

## 🧰 Basic Linux Commands Used in Cybersecurity

### 📡 Network & Recon

* ping `target`
* nslookup domain.com
* whois domain.com
* curl -I target

### 🔍 Port & Service Checks

* nmap -sV target
* netstat -tulnp
* ss -tulnp

### 🛡️ System Security

* ufw status
* sudo ufw enable
* systemctl status ssh

### 📁 File & Permissions

* ls -la
* chmod 777 file
* chown user:user file
* find / -name "file"

---

## 🎯 Purpose

This toolset is created for:

* Cybersecurity learning
* Network fundamentals understanding
* Ethical security practice
* Bug bounty preparation

---

## ⚠️ Disclaimer

This project is strictly for educational and authorized security testing purposes only. Unauthorized scanning of systems without permission is not allowed.
