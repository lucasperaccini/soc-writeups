# MITRE ATT&CK — Writeup

**Type:** Concept / self-study · **Source:** attack.mitre.org · **Date:** 2026-10-22

## 1. Overview
MITRE ATT&CK is a public knowledge base of **adversary tactics and techniques** based
on real-world observations. It gives defenders a **common language** to describe *how*
attackers behave. For a SOC analyst it's the backbone for mapping alerts, measuring
detection coverage, and communicating findings clearly.

## 2. How it's structured
- **Tactics** – the attacker's *goal* ("the why"). e.g. *Initial Access, Persistence, Exfiltration*.
- **Techniques** – *how* they achieve that goal ("the how"). e.g. *T1566 – Phishing*.
- **Sub-techniques** – a more specific variant. e.g. *T1566.001 – Spearphishing Attachment*.
- **Procedures** – the concrete way a specific group implements a technique.

There are several **matrices**: *Enterprise*, *Mobile*, and *ICS*. The Enterprise matrix
is the most used in a SOC.

## 3. The Enterprise tactics (the columns)
Reconnaissance · Resource Development · Initial Access · Execution · Persistence ·
Privilege Escalation · Defense Evasion · Credential Access · Discovery ·
Lateral Movement · Collection · Command and Control · Exfiltration · Impact.

## 4. How a SOC uses ATT&CK
- **Alert mapping:** tag each alert with its technique ID (e.g. T1110) to speak a common language.
- **Detection coverage:** see which techniques you can/can't detect (gap analysis).
- **Threat intel:** threat reports describe groups by the techniques they use.
- **Triage:** knowing the technique helps decide severity and next steps.

## 5. Example technique
**T1055 – Process Injection** (tactic: *Privilege Escalation* / *Defense Evasion*).
The attacker injects malicious code into a legitimate running process to gain higher
privileges and blend in with normal activity. In logs it could show as an unexpected
process accessing or writing into the memory of another process — for example, Sysmon
**Event ID 8** (CreateRemoteThread) or **Event ID 10** (ProcessAccess).

## 6. Connection to the Cyber Kill Chain
The Kill Chain gives the **high-level phases**; ATT&CK fills each phase with **specific
techniques**. Example: Kill Chain "Delivery" ↔ ATT&CK **T1566 – Phishing**.

## 7. Tool
**ATT&CK Navigator** – a free web tool to visualize techniques on the matrix and mark
detection coverage.

## 8. Key takeaway
ATT&CK turns "something suspicious happened" into "this is technique T#### in tactic X",
which makes triage, communication, and detection measurable.

## 9. Next
Use ATT&CK Navigator to map the techniques I can already detect vs. the gaps.
