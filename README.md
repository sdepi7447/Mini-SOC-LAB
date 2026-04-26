# Mini SOC Lab

## Overview

This project demonstrates a **Mini Security Operations Center (SOC) Lab** built to simulate real-world monitoring and detection scenarios.
The lab integrates multiple systems to collect, analyze, and visualize logs for security monitoring.

---

## Lab Architecture

The lab consists of three main machines:

  **Ubuntu Server**

  Hosts **Wazuh Manager**
  * Responsible for log analysis, alerting, and visualization

   **pfSense Firewall**

  * Acts as the network firewall
  * Configured to send logs via **Syslog**
  * Includes **Squid Proxy** for web traffic monitoring

   **Windows 10 Machine**

  * Installed **Wazuh Agent**
  * Sends endpoint logs to Wazuh Manager
  * Installed **sysmon** to improve visability

---

## Technologies Used

* Wazuh (SIEM & XDR)
* pfSense (Firewall)
* Syslog (Log forwarding)
* Squid Proxy (Web monitoring)
* Windows 10 (Endpoint)
* Sysmon (Endpoint monitoring)
* Ubuntu Server (Wazuh Manager)
* Atomic red team (attacks simulation)

---

## Data Flow

1. Windows machine generates logs → sent via Wazuh Agent
2. pfSense firewall logs → forwarded using Syslog
3. Squid Proxy logs → captured for web traffic analysis
4. All logs → analyzed by Wazuh Manager on Ubuntu

---

##  Setup Steps (High-Level)

1. Install Wazuh Manager on Ubuntu
2. Install Wazuh Agent on Windows 10
3. install sysmon
4. Configure agent to connect to Wazuh Manager
5. Enable Syslog on pfSense and forward logs to Wazuh
6. Install and configure Squid Proxy on pfSense
7. Forward Squid logs to Wazuh

---

##  Use Cases

* Detect suspicious login activity
* Monitor firewall traffic
* Analyze web browsing behavior via proxy
* Correlate logs across multiple sources

## Attack Simulation (Atomic Red Team)

To simulate real-world attack scenarios, we used **Atomic Red Team** to execute controlled adversary techniques mapped to the MITRE ATT&CK framework.

### What was implemented:

* Executed multiple attack techniques on the Windows 10 machine
* Generated realistic security events and logs
* Tested detection capabilities of Wazuh

### Objectives:

* Validate log collection from endpoints and firewall
* Test alert generation and detection rules in Wazuh
* Simulate attacker behavior in a controlled lab environment

### Example Scenarios:

* Credential Access simulation
* Privilege Escalation attempts
* Suspicious PowerShell execution
* Network reconnaissance activities

### Outcome:

* Successfully detected multiple attack patterns
* Correlated logs between Windows endpoint and pfSense
* Improved visibility into attacker techniques

---

## Goals

* Build hands-on SOC experience
* Understand log collection and correlation
* Practice threat detection techniques

---

---

## Team

Youssef Mohammed Abdelnaeim
Habiba Mahmoud
Habiba Ahmed
Mohamed gamal

---
