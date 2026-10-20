# OC-Analyst-Playbooks
# Incident Response Playbook: Initial Phishing & Credential Access Triage

## Overview
This playbook defines the Standard Operating Procedure (SOP) for a Junior SOC Analyst during the initial triage of suspected phishing attempts and potential credential compromise alerts.

## Framework Alignment & Core Controls
- **NIST CSF Alignment:** Detect (DE.AE-1), Respond (RS.AN-1)
- **CIA Triad Focus:** Confidentiality (Primary), Integrity

## Operational Triage Procedure

### Step 1: Incident Categorization
* **Alert Source:** Email Security Gateway / EDR Alert
* **Threat Type:**
  * *External Threat:* Inbound phishing email containing malicious URL/attachment.
  * *Internal Threat (Accidental):* Employee interaction with external malicious link.

### Step 2: Immediate Containment Actions
1. **Network Isolation:** Isolate the target host from the local network via EDR console to prevent lateral movement.
2. **Identity Revocation:** Invalidate active user sessions and initiate a forced password reset in Active Directory / AWS IAM.
3. **Perimeter Blocking:** Add malicious IPs, domains, and file hashes (SHA-256) to the perimeter firewall and gateway blocklists.

### Step 3: Evidence Documentation
* Record the incident timestamp, host IP/MAC address, target account ID, and indicators of compromise (IoCs) within the ticketing system.
* Escalate to Tier-2 SOC if active post-exploitation activity or privilege escalation is detected.

---
*Author:  Mariano Schiavone | Defensive Security Analyst*
