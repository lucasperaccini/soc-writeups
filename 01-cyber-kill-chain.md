# Cyber Kill Chain — Writeup

**Type:** Concept / self-study · **Source:** Lockheed Martin Cyber Kill Chain · **Date:** 22/10/2026

## 1. Overview
The Cyber Kill Chain is a model by Lockheed Martin that breaks an intrusion into
7 sequential phases. For a SOC analyst it's useful because the **earlier** you detect
an attacker in the chain, the **less damage** they can do — the goal is to "break the
chain" as soon as possible.

## 2. The 7 phases (and what a SOC sees)

| # | Phase | Attacker action | What a SOC analyst might detect |
|---|-------|-----------------|---------------------------------|
| 1 | Reconnaissance | Gathers information about the target | Port scans, unusual web traffic, OSINT against the org |
| 2 | Weaponization | Prepares the exploit / payload | Usually not visible (happens on attacker side) |
| 3 | Delivery | Sends it (phishing, USB, web) | Suspicious emails at the mail gateway, malicious attachments/links |
| 4 | Exploitation | Code runs and exploits a vulnerability | Unexpected process execution, crashes, EDR/antivirus alerts |
| 5 | Installation | Installs persistence (malware, backdoor) | New services, registry run keys, scheduled tasks, new files |
| 6 | Command & Control (C2) | Controls the machine remotely | Unusual outbound traffic, beaconing, connections to rare domains/IPs |
| 7 | Actions on Objectives | Steals data, encrypts, moves laterally | Large data transfers, lateral movement, mass file changes (ransomware) |

## 3. Why it matters for defense
Each phase is a chance to detect and stop the attack. Detecting at **Delivery**
(a phishing email) is far cheaper than detecting at **Actions on Objectives**
(data already stolen). The model helps a SOC prioritize where to put detection.

## 4. Connection to MITRE ATT&CK
The Kill Chain gives the **high-level phases**; MITRE ATT&CK breaks each phase into
**specific techniques**. Example: "Delivery" maps to **T1566 – Phishing**;
"Credential Access" during later stages maps to techniques like **T1110 – Brute Force**.

## 5. Key takeaway
Think in terms of "where in the chain am I seeing this, and how do I break it earlier
next time?" — that mindset is the core of SOC triage.

## 6. Next
Go deeper into MITRE ATT&CK to map real techniques to each phase.
