# Systems as Attack Vectors

## Room Information

* Platform: TryHackMe
* Path: SOC Level 1
* Room: Systems as Attack Vectors
* Status: In progress
* Type: Practical Notes / Mini Workflow
* Main Topic: How attacks exploit vulnerable and misconfigured systems and how SOC analysts can protect and prevent them

## 1. Objective

This room focuses on how a SOC analyst can protect systems as well as why and how systems are exploited and targeted by attackers.

## 2. Key Concepts Learned

### Concept 1: What is a System?

Even with advanced protocols that identify and protect systems against exploitation of human behavior, if the lock of the castle is fragile then the attacker can break in without notice.

**System** -> the heart of where data is stored

Attacker's POV:
Breach one user email -> access a single mailbox
Compromise mail server -> control thousands of mailboxes

| Breached System | Attack Value |
| -------- | ------- |
| A student personal computer | Steal steam profile and add PC to a botnet |
| Mail server of criminal law company | Blackmail victim and dump all mailboxes |

---

### Concept 2: Attacks on systems

All attacks start out the same way with the goal to gain **access** to the target system.

| Types of Attack | Meaning | Example |
| -------- | ------- | ------- |
| Human-Led | System users start the attack | Inserting a suspicious USB found on the street |
| Vulnerabilities | Software Security flaws | Zero days, Outdated Windows hosts |
| Supply Chain | Comprising an app or its library present on your PC and pushing an update to all its users | SolarWinds breach |

---

### Concept 3: Vulnerabilities

**Zero-day** -> when an attacker discovers a vulnerability before anyone does

**CVE number** (Common Vulnerabilities and Exposures) -> assigned when a vulnerability is made public -> also the start of the race for attackers and defenders

CVE answer -> **a patch** (update)

---

### Concept 4: Misconfigurations

**Misconfiguration** -> mistake in how the system was setup -> for example having a weak password or having unrestricted access

Response -> **better setup**

---

### Concept 5: Mitigation

M1: Patched software -> M2: Antivirus solution -> SOC team handle the rest

Most common mitigation measures for system protection
| Mitigation | Description |
| -------- | ---------- |
| Patch management | Track and patch vulnerabilities of systems |
| Training for IT | Train IT team of the risks of misconfigurations |
| Network protection | Restrict system to trusted IP and people |
| Antivirus Solution | Detect/stop many attacks |

---

## 3. Systems at Risk Breakdown

| Risk Alert | Breach Factor | Remediation Plan |
| -------- | -------- | -------- |
| Mail server affected by CVE-2024-49040 | Software vulnerability | Patch |
| Brute-force admin panel of website and placed malware links | Credentials | Change admin password to a secure password |
| Trusted 3D application starts running malicious CMD commands after recent updates | Supply chain attack | Investigate the supply chain attack with the update |

## 4. SOC Analyst Perspective

### What I would monitor

*
*
*

### Possible alerts

*
*
*

### Investigation questions

* What system was affected?
* What user account was involved?
* What IP address, domain, or service was involved?
* Was the activity successful or only attempted?
* Was there unusual login activity?
* Was any file downloaded or executed?
* Were any permissions changed?
* Was there evidence of lateral movement?
* Was any sensitive data accessed?
* Does this need escalation?

### Possible response steps

*
*
*

---

## 5. Defensive Recommendations

### Technical controls

*
*
*

### Monitoring and detection controls

*
*
*

### Process improvements

*
*
*

---

## 6. Mini Case Study

### Scenario

Scenario:

### What happened

What happened:

### Initial indicator

Initial indicator:

### Investigation steps

*
*
*

### Potential impact

Potential impact:

### Recommended containment

Recommended containment:

### Long-term prevention

Long-term prevention:

---

## 7. Reflection

### What I learned

What I learned:

### What confused me at first

What confused me at first:

### How this connects to SOC Level 1 work

How this connects to SOC Level 1 work:

### What I want to learn next

What I want to learn next:

---

## 8. Skills Demonstrated

*
*
*
*
*
