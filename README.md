# 🛡️ SOC Internship Task: Security Alert Monitoring & Incident Response

This project simulates real-world Security Operations Center (SOC) responsibilities by using **Splunk** as a Security Information and Event Management (SIEM) tool to monitor logs, detect suspicious activities, and respond to potential security incidents.

## 📌 Overview

This internship task involved analyzing simulated security logs using Splunk to detect key threats such as:
- Brute-force login attempts
- Credential stuffing
- Malware infections
- Suspicious PowerShell execution (T1059.001)

The goal was to build practical skills in alert detection, investigation, incident classification, and formal SOC-style documentation.

---

## ✅ Objectives

- Set up and explore Splunk (Free Trial)
- Upload and analyze simulated `.csv` logs
- Detect 3–5 suspicious security events
- Classify alerts by severity (High, Medium, Low)
- Draft an Incident Response Report
- Capture screenshots as evidence
- Simulate stakeholder communication

---

## 🛠️ Tools & Environment

- **Splunk Cloud** (Free Trial)
- **CSV Log File**: `soc_simulated_logs.csv`
- **Screenshot Tool**: Snipping Tool / OS Shortcut
- **Report Tool**: MS Word / Google Docs

---

## 🔍 Key Splunk Queries Used

### 1. Detect 5+ Failed Logins from Same IP/User
```spl
source="*soc_simulated_logs.csv" "Failed Login"
| stats count by user, src_ip
| where count >= 5
```

### 2. Logins from Public IPs (203.x.x.x)
```spl
source="*soc_simulated_logs.csv" "Successful Login"
| where src_ip LIKE "203.%"
```

### 3. Malware Detection Events
```spl
source="*soc_simulated_logs.csv" "Malware Detection"
| table timestamp, user, src_ip, host, signature
```

### 4. Risk Event: PowerShell Encoded Command
```spl
source="*soc_simulated_logs.csv"
| search "powershell" "enc"
```

---

## 📸 Included Screenshots

- Splunk alert for PowerShell encoded command
- Brute-force login attempts
- Public IP logins
- MITRE ATT&CK mapping (T1059.001)
- User risk score summary
- Event timeline visualization

---

## 📄 Deliverables

- `Incident_Response_Report.pdf`: A structured summary of detected threats, investigation steps, decoded payloads, and mitigation recommendations.
- `soc_simulated_logs.csv`: Sample log file used in Splunk
- `Screenshots` folder: Supporting visual evidence for each detection
- `README.md`: This file – explaining the project structure and process

---

## 🧠 Skills Gained

- Basic SIEM operation and log ingestion
- Detection of security threats in Splunk
- Incident triage and response strategy
- Documentation and communication of security incidents

---

## 📬 Contact

- **Intern Name:** Nischaya
- **Organization:** Future Interns
- **Date Completed:** June 2025