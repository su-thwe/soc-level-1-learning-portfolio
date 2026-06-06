# Security Incident Report: [Incident Name]

## 1. Executive Summary

Briefly summarize the incident in 3–5 sentences.

Include:
- What happened
- What system/user/business area was affected
- How it was discovered
- Main suspected or confirmed cause
- Recommended next step

Example structure:

> [System/service] experienced [incident type]. The issue was identified through [logs/user report/alert/sandbox analysis]. Evidence showed [main technical finding]. The likely root cause was [cause]. Recommended remediation is [control/action].

---

## 2. Incident Details

| Field | Details |
|---|---|
| Date/Time | [Date/time or “Not specified”] |
| Affected System(s) | [System, application, endpoint, network, account, etc.] |
| Incident Type | [Phishing, malware, brute force, web compromise, suspicious login, etc.] |
| Detection Method | [User report, SIEM alert, log review, tcpdump, EDR alert, etc.] |
| Severity | [Low / Medium / High, if known] |
| Status | [Open / Investigating / Contained / Resolved] |

---

## 3. Evidence Reviewed

| Evidence Source | Observation |
|---|---|
| [Log file/tool output] | [What the evidence showed] |
| [User report] | [What was reported] |
| [Network capture] | [Relevant traffic observed] |
| [System review] | [Relevant system finding] |

---

## 4. Technical Analysis

### Relevant Protocols, Tools, or Services

| Protocol / Tool / Service | Role in the Incident |
|---|---|
| [DNS / HTTP / TCP / etc.] | [What role it played] |
| [Tool name] | [What it was used to identify] |

### Analysis Summary

Explain the technical flow of the incident.

Include:
- What happened first
- What systems communicated
- What logs or traffic patterns were observed
- What behavior was suspicious
- What evidence supports your conclusion

---

## 5. Incident Timeline

| Step | Event |
|---|---|
| 1 | [First observed event] |
| 2 | [Second event] |
| 3 | [Third event] |
| 4 | [Containment or investigation step] |

---

## 6. Root Cause

Explain the main cause of the incident.

Possible examples:
- Weak/default password
- Missing MFA
- User clicked a phishing link
- Unpatched software
- Misconfigured firewall rule
- Lack of monitoring
- Exposed service

Root cause:

> [Write your explanation here.]

---

## 7. Impact

Describe what was affected.

Include:
- Affected users
- Affected systems
- Data exposure, if any
- Business impact
- Security impact

Impact summary:

> [Write your explanation here.]

---

## 8. Recommended Remediation

### Recommended Control

[Name one main control or action.]

### Why This Helps

Explain how the recommendation reduces the chance of this incident happening again.

Examples:
- Enforce multi-factor authentication
- Limit failed login attempts
- Disable default credentials
- Improve logging and alerting
- Block malicious domains
- Patch vulnerable systems
- Train users on phishing indicators

Recommendation:

> [Write your recommendation here.]

---

## 9. Lessons Learned

List practical takeaways from the incident.

- [Lesson 1]
- [Lesson 2]
- [Lesson 3]

---

## 10. References / Sources

List the evidence or learning sources used.

- [Log file]
- [Scenario description]
- [Tool output]
- [Course/lab material]
- [Internal documentation]