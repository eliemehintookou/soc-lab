# 🔐 SOC Lab – Real-World Detection Project

Hands-on cybersecurity lab simulating a Security Operations Center (SOC) with intrusion detection and log analysis.

## 🎯 Project Overview

This project simulates a basic Security Operations Center (SOC) environment using open-source tools to detect and analyze security events.

The goal is to understand how network traffic and system logs can be monitored, analyzed, and correlated to identify suspicious activity.

---

## 🧰 Technologies Used

* Ubuntu (Virtual Machines)
* Suricata (IDS)
* Wazuh (SIEM)
* Nmap
* Linux logs (auth.log)
* VirtualBox

---

## 🏗️ Architecture

* **VM 1 (Agent)**:

  * Suricata IDS
  * System logs (/var/log/auth.log)
  * Simulated attacks

* **VM 2 (Manager)**:

  * Wazuh Manager
  * Wazuh Indexer
  * Wazuh Dashboard

---

## 🔍 Use Cases

### 1. Network Activity Detection (ICMP)

* Generated traffic using ping
* Detected using Suricata
* Logs stored in:

  * fast.log
  * eve.json

---

### 2. SSH Brute Force Simulation

* Multiple failed login attempts
* Logs analyzed in:

  * /var/log/auth.log

---

### 3. Log Analysis

* Used tools:

  * grep
  * tail
* Investigated events in:

  * Suricata logs (JSON format)
  * System logs

---

## 📸 Proof of Work

Screenshots available in `/screenshots`:

* ICMP detection alerts
* SSH failed login attempts
* Suricata logs (eve.json)
* Active services (Suricata & Wazuh)

---

## 🚀 Key Skills Developed

* Network monitoring
* Intrusion detection (IDS)
* Log analysis
* Incident investigation
* SIEM fundamentals
* Linux administration

---

## ⚠️ Notes

Wazuh dashboard deployment was successful, but web access may be limited in a virtualized environment due to networking constraints.

---

## 📌 Future Improvements

* Full SIEM integration (agent → manager)
* Alert correlation
* Advanced attack simulations (Nmap, Hydra)
* Dashboard tuning


## 📸 Screenshots

### ICMP Detection
![ICMP](screenshots/icmp-detection.png)

### SSH Attack Detection
![SSH](screenshots/ssh-failed-login.png)

### JSON Log Analysis
![JSON](screenshots/eve-json-analysis.png)

###Network Scan Detection (Nmap)

![Nmap](screenshots/scan.png)

## 🏗️ Architecture

![Architecture](architecture/architecture.png)

---

### Network Scan Detection (Nmap)

A SYN scan was performed using Nmap and analyzed in real time using tcpdump.

Observed TCP flags:
- SYN (connection attempt)
- SYN-ACK (response)
- RST (connection reset)

This demonstrates how reconnaissance activity can be identified at packet level.


## ⚙️ How to Reproduce

### 1. Install Suricata

```bash
sudo apt update
sudo apt install suricata -y
```

### 2. Start Suricata

```bash
sudo systemctl start suricata
```

### 3. Generate Network Traffic

```bash
ping -c 4 8.8.8.8
```

### 4. Check Alerts

```bash
sudo tail -n 10 /var/log/suricata/fast.log
```

### 5. Simulate SSH Attack

```bash
sudo grep "Failed password" /var/log/auth.log
```

### 6. Run Nmap Scan

```bash
sudo nmap -sS -p 1-100 127.0.0.1
```

### 7. Analyze Traffic

```bash
sudo tcpdump -i lo tcp
```


## 📚 Lessons Learned

* Understanding how network traffic can be analyzed at packet level (TCP flags)
* Identifying brute force attacks through system logs
* Using Suricata for intrusion detection
* Deploying a SIEM (Wazuh) for log management
* Troubleshooting network and configuration issues in a virtual lab environment


## Final Troubleshooting Phase

The lab environment successfully achieved:

- Wazuh Manager deployment
- Wazuh Agent installation
- Suricata IDS deployment
- Internal network segmentation
- Agent enrollment
- Port accessibility validation
- SIEM architecture deployment

During the final integration phase, TCP communication on port 1514 reached the manager successfully, but the service returned a "Connection refused" response.

This troubleshooting phase provided practical experience in:
- Linux networking
- VirtualBox internal networking
- SIEM troubleshooting
- Wazuh agent/manager communication
- TCP service validation

## 👨‍💻 Author

MEHINTO OKOU Elie Virgile  – SOC Analyst path
