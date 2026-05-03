# 🔐 SOC Lab – Detection & Monitoring Project

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

---

## 👨‍💻 Author

MEHINTO OKOU Elie Virgile  – SOC Analyst path
