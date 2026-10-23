
# Pyramid of Pain — Writeup

**Type:** Concept / self-study · **Source:** David Bianco — "Enterprise Detection & Response" · **Date:** 2026-10-22

## 1. Overview
The Pyramid of Pain, by David Bianco, ranks the **indicators of compromise (IOCs)** a
defender can detect by **how much pain it causes the attacker** when that indicator is
detected and blocked. The key idea: the harder an indicator is for the attacker to
change, the more valuable it is for a SOC to detect.

## 2. The 6 levels (listed from the top of the pyramid down to the base)

| Level | Indicator | How hard for the attacker to change | Pain |
|-------|-----------|-------------------------------------|------|
| 6 (top) | **TTPs** | Change their whole way of operating (behavior) | 🔴 Tough |
| 5 | **Tools** | Find or build a new tool | 🟠 Challenging |
| 4 | **Network / Host artifacts** | Modify their tooling to change the traces it leaves | 🟡 Annoying |
| 3 | **Domain names** | Register a new domain (costs time/money) | 🟢 Simple |
| 2 | **IP addresses** | Switch to another IP | 🟢 Easy |
| 1 (base) | **Hash values** | Change one byte of the file → new hash | ⚪ Trivial |
## 3. The core idea
- **Bottom** = data the attacker can change **in seconds** (hash, IP). Blocking it barely
  slows them down.
- **Top** = **behaviors** (TTPs) the attacker can almost **never** change easily.
  Detecting at this level forces them to rebuild how they attack.

So a hash is cheap to detect but cheap for them to bypass; a TTP is hard to detect but,
once you do, it really hurts the adversary.

## 4. What TTPs are
**TTP = Tactics, Techniques & Procedures** — the attacker's objective (*why*), method
(*how*), and the specific way they carry it out. It's their "style" of operating.
Example: *spearphishing for access → Mimikatz to dump credentials → RDP for lateral
movement.*

## 5. Connection to MITRE ATT&CK
The **top of the pyramid (TTPs)** is exactly what **MITRE ATT&CK** catalogs. That's why
ATT&CK matters so much for a SOC: it helps you detect the attacker at the level that
causes them the **most pain** — their behavior.

## 6. SOC takeaway
Detections built on **behavior (TTPs)** are more durable than detections built on
**hashes or IPs**, which attackers rotate constantly. A mature SOC aims higher up the
pyramid.

## 7. Next
Study how specific ATT&CK techniques map to detections, moving beyond simple IOC blocking.
