# Humans as Attack Vectors

## Room Information

- Platform: TryHackMe
- Path: SOC Level 1
- Room: Humans as attack vectors
- Status: Completed
- Type: Practical Notes / Mini Workflow
- Main Topic: Human as attack vectors

## 1. Objective

This room explores how human behavior is exploited by attackers along with how defenders help defend, detect, prevent and respond to them.

## 2. Key Concepts Learned

### Concept 1: Human Element

Attacker's POV: ask the gatekeeper to open the door, no point in breaking the gates. Humans provide access so target them.

| Initial Attack | Human Factor Exploited | Attack Progression |
|------------|------------|------------|
| Compromise an executive's email account  | Trust in authority, lack of verification | Send fraudulent payment requests or impersonate executive |

### Concept 2: Attacks on Humans

Social engineering -> exploit human psychology
A successfully designed tactic -> trustworthy and emotional.

### Attack Vector Breakdown

| Attack Vector | Description | Human Behavior Exploited | Possible Business Impact | Possible Indicators | Defensive controls |
|------------|------------|-------------|-------------|-------------|-------------|
| Phishing | An attacker sends a message that appears to come from a trusted source. The message will usually convince the user to interact with the message. | Trust, fear, curiosity, urgency | Credential theft, account compromise, malware, data exposure | Suspicious sender address, mismatched domains, suspicious links or attachments | Email filtering, phishing awareness training, MFA |
| Malware Downloads | An attacker tricks the user to open or download a malicious file such as a fake document, installer, or attachment | Curiosity, urgency, lack of verification | Endpoint compromise, data exposure, credential theft, malware infection | Unexpected file download, fake CAPTCHAs, browser redirects, strange device behavior | least privilege, user awareness training, block unsafe file types, Antivirus/EDR |
| Deepfakes | An attacker uses AI-generated audio, video or images to impersonate loved ones or colleagues with the intent of convincing someone to send money, share credentials or reveal sensitive information. | Lack of verification, trust in authority, familiarity, urgency | Fraudulent payments, credential theft, data leakage, unauthorized access | Unknown urgent requests, slightly unnatural facial or audio, mismatched communication | MFA, awareness training, deepfake detection tools, payment verification policies |

### Concept 3: Defending Humans

Involves two key tasks:
1. Mitigation
2. Detection

M1: Anti-phishing tool -> M2: Employee Training -> SOC team handles the rest

Types of Mitigations:

1. Anti-phishing solution - Tool that blocks phishing emails before it reaches the user
2. Antivirus/EDR solution - Antivirus on hosts would help prevent humans from running malware
3. "Trust but verify" principle - Train employees to detect and verify suspicious requests
4. Security awareness training - Teach and train employees how to detect phishing through simulations and awareness

---

## SOC Analyst Perspective

### What I would monitor

- Email security logs for suspicious senders, links, attachments, spoofed domain, and mass-email patterns.
- Endpoint alerts for downloaded files, suspicious process execution, malware detections or unusual browser activity.
- Authentication logs for unusual sign-ins, failed login attempts, new devices, or MFA fatigue attempts.

### Possible alerts

- Sign-in from an unusual location, IP address or device
- Multiple failed login attempts
- Endpoint downloaded or executed a suspicious file
- User reported a phishing or impersonation attempt

### Investigation questions

- Who received the message?
- Did anyone click the link?
- Did anyone submit credentials?
- Was MFA triggered?
- Was there a suspicious login afterward?
- Were any mailbox rules created?
- Were files accessed or downloaded?

### Possible response steps

- Confirm which users received or interacted with the suspicious message
- Remove the phishing attempt from defined endpoint
- Isolate affected endpoints if malicious code was executed
- Escalate to the incident response team if credentials, files, or systems were accessed or breached.

---

## 5. Mini Case Study

Scenario: An employee receives an email that appears to come from a senior manager. The message says an invoice must be review urgently and includes a link to download the document.

What happened: The attacker used authority and urgency to pressure the employee into trusting and responding to the message. The link redirected the employee to a suspicious website that attempted to download a malicious file.

Initial indicator: The employee reported the email since they noticed slight differences from the company's domain in the sender's address.

Investigation steps:
- Review email headers, sender address, links, and attachment details
- Check if this email is spreading to others
- Search DNS logs to see whether anyone visited the link
- Check endpoint logs to confirm whether the file was downloaded or executed.
- Review authentication logs for suspicious sign-ins after the email was received.

Potential impact: Credential theft, malware infection, data exposure, unauthorized access, or email compromise.

Recommended containment: Block the sender and malicious domain, remove the email from inboxes, reset credentials for affected users, revoke sessions, and isolate endpoints that executed the file.

Long-term prevention: Improve phishing training, enforce MFA, strength email filtering and apply "Trust but verify" principle.

---

## 7. Reflection

What I learned: The main reason for why humans are the weakest link in complex systems.

How this connects to SOC Level 1 work: SOC analysts need to investigate suspicious emails, user reports, login alerts, endpoint detections, and signs of account compromise.

What I want to learn next: How automation helps a SOC analysts daily work and how its coded.

---

## 8. Skills Demonstrated

- Social engineering risk analysis
- Phishing detection mindset
- SOC investigation thinking
- Security awareness
- Incident response basics
- Defensive documentation