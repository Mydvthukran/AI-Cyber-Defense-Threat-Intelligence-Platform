# AI Cyber Defense Threat Intelligence Platform

A simple SOC/SIEM-style cybersecurity project to capture traffic, detect threats, visualize attacks, and optionally respond automatically.

## Project Flow (Simple)

### 1) Network Traffic Comes In
Traffic enters from websites, logins, downloads/uploads, and API calls.

- Packet capture tools: **Wireshark**, **Suricata**
- Packets are treated as small data messages moving across the network

### 2) Traffic Monitoring
The system watches packets in real time and checks:

- Source/destination IPs
- Ports and protocols
- Packet/request type
- Request frequency

Examples:
- Normal browsing ✅
- 500 login attempts in 1 minute 🚨
- Port scanning behavior 🚨

### 3) Threat Detection Engine
Two detection methods work together:

**A. Rule-Based Detection (Snort/Suricata rules)**
- Example: if failed login attempts exceed threshold → trigger alert

**B. AI/ML Detection**
- Learns normal behavior and flags anomalies
- Example: normal user ~20 requests/min vs attacker ~2000 requests/min

### 4) Alert Generation
When suspicious activity is detected:

- Dashboard shows warning
- Admin gets notification
- Logs are stored for investigation

Common alerts:
- Port scan detected
- Brute-force attack detected
- Suspicious IP activity
- Malware-like traffic pattern

### 5) Visualization Dashboard
Frontend displays live security status:

- Attack graphs
- Traffic charts
- Attacker IP list
- Threat severity
- Real-time event logs

Suggested stack: **React + Chart.js**

### 6) Auto Response (Advanced)
Optional automated actions:

- Block IPs
- Rate-limit/stop abusive requests
- Isolate suspicious traffic

Example: too many requests from one IP → auto-blacklist.

### 7) Honeypot (Advanced)
Deploy a fake vulnerable target to study attackers safely.

- Suggested tool: **Cowrie**
- Captures attacker behavior, commands, and patterns for threat intelligence

## Very Simple Architecture

```text
Network Traffic
      ↓
Packet Capture
      ↓
Threat Detection Engine
      ↓
AI Analysis + Security Rules
      ↓
Alerts + Logs
      ↓
Dashboard Visualization
      ↓
Auto Response / Blocking
```

## Roles (Short)

- **SOC Analyst**: monitors dashboard, validates alerts, escalates incidents.
- **Security Engineer**: writes/tunes detection rules, manages Suricata/Snort, response policies.
- **ML Engineer**: builds and improves anomaly detection models.
- **Backend Engineer**: builds ingestion APIs, detection orchestration, alert services.
- **Frontend Engineer**: develops dashboard, charts, and live incident views.
- **DevOps/Platform Engineer**: deployment, scaling, logging pipeline, reliability.

## Requirements (Short)

### Core Tools
- Packet capture/IDS: Wireshark, Suricata (and/or Snort rules)
- Honeypot (optional): Cowrie
- Frontend: React, Chart.js
- Backend/ML stack (recommended): Python + FastAPI + scikit-learn

### Infrastructure
- Linux environment for network tooling
- Local lab/test network for safe attack simulation
- Database/log storage (e.g., PostgreSQL/Elasticsearch) for alerts and history

### Safety
- Run attack simulations only in authorized lab environments.
- Never test offensive techniques on public or unauthorized systems.

## Repository Structure

```text
AI-Cyber-Defense-Threat-Intelligence-Platform/
├── backend/
├── frontend/
└── README.md
```
