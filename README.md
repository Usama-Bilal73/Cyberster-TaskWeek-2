# Purple Team Lab: Reconnaissance & Defensive Implementation

## 📌 Project Summary
This repository contains the documentation and technical findings for a Purple Team security assessment. The project focuses on mapping an attack surface through Stealth Scanning and Service Fingerprinting, followed by the validation of defensive monitoring systems.

## 🛠️ Environment & Tools
- **Platform:** VMware Workstation (Isolated LAN Segment)
- **Attacker Node:** Kali Linux (Adversary OS)
- **Target Node:** Windows 10 (Target Asset)
- **Tools Used:** - `Nmap`: For active host discovery and service versioning.
  - `Wireshark`: For deep packet inspection and protocol forensics.
  - `Test-NetConnection`: For baseline connectivity verification.

## 🚀 Operational Workflow

### Phase 1: Offensive Reconnaissance
1. **Host Discovery:** Initial sweep to identify the target IP (192.168.88.1).
2. **Stealth Scanning:** Executed `Nmap -sS` (SYN Scan) to map open ports without completing the TCP handshake.

3. **Service Fingerprinting:** Identified the SMB protocol running on Port 445, marking it as a high-priority vulnerability.

### Phase 2: Defensive Analysis
1. **Traffic Forensics:** Analyzed captured traffic to identify "Reset" (RST) packets, which serve as a signature for stealth scanning activity.
2. **Engine Validation:** Verified that the monitoring engine on the `eth0` interface successfully ingests and processes automated scan traffic.

## 📊 Key Findings
- **Vulnerability:** Port 445 (SMB) is exposed.
- **Risk Level:** High (Potential for MS17-010 or Ransomware exploits).
- **Recommendation:** Implement host-based firewall rules to restrict SMB access and apply critical security patches.

## 📜 Conclusion
The lab successfully demonstrates a "Purple Team" feedback loop where offensive findings directly inform defensive readiness. The environment is now prepared for the next stage: Exploitation and Remediation.
