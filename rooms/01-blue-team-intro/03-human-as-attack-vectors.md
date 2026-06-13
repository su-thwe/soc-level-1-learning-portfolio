# Humans as Attack Vectors

## Room Information

- Platform: TryHackMe
- Path: SOC Level 1
- Room: Humans as attack vectors
- Status: In progress
- Type: Practical Notes / Mini Workflow
- Main Topic: How human behavior is exploited by attackers along with how defenders helps defend, detect, prevent and respond to them

## 1. Objective

This room 

## 2. Key Concepts Learned

### Concept 1: Human Element 

Attack's POV: ask the gatekeeper to open the door, no point in breaking the gates. Humans provide access so target them.

| Initial Attack | Human Factor Exploited | Attack Progression | 
|------------|------------|------------|
| Compromise an executive's email account  | Trust in authority, lack of verification | Send fraudulent payment requests or impersonate executive | 

---

### Concept 2: Attacks on Humans

Social engineering -> exploit human psychology 
A successfully designed tactic is designed to be trustworthy and emotional.

### Attack Vector Breakdown

| Attack Vector | Description | Human Behavior Exploited | Possible Business Impact | Possible Indicators | Defensive controls |
|------------|------------|-------------|-------------|-------------|-------------|
| Phishing | An attacker sends a message that appears to come from a trusted source. The message will usually convince the user to interact with the message. | Trust, fear, curiosity, urgency | Credential theft, account compromise, malware, data exposure | Suspicious sender address, mismatched domains, suspicious links or attachments | Email filtering, phishing awareness training, MFA |  
| Malware Downloads | An attacker tricks the user to open or download a malicious file such as a fake document, installer, or attachment | Curiosity, urgency, lack of verification | Endpoint compromise, data exposure, credential theft, malware infection | Unexpected file download, fake CAPTCHAs, browser redirects, strange device behavior | least privilege, user awareness training, block unsafe file types, Antivirus/EDR |
| Deepfakes | An attacker uses AI-generated audio, video or images to impersonate loved ones or colleagues with the intent of convincing someone to send money, share credentials or reveal sensitive information. | Lack of verification, trust in authority, familiarity, urgency | Fraudulent payments, credential theft, data leakage, unauthorized access | Unknown urgent requests, slightly unnatural facial or audio, mismatched communication | MFA, awareness training, deepfake detection tools, payment verification policies |

---

## 4. SOC Analyst Perspective

### What I would monitor

- 
- 
- 

### Possible alerts

- 
- 
- 

### Investigation questions

- Who received the message?
- Did anyone click the link?
- Did anyone submit credentials?
- Was MFA triggered?
- Was there a suspicious login afterward?
- Were any mailbox rules created?
- Were files accessed or downloaded?

### Possible response steps

- 
- 
- 

---

## 5. Defensive Recommendations

### Technical controls

- 
- 
- 

### User-awareness controls

- 
- 
- 

### Process improvements

- 
- 
- 

---

## 6. Mini Case Study

Scenario:

What happened:

Initial indicator:

Investigation steps:

Potential impact:

Recommended containment:

Long-term prevention:

---

## 7. Reflection

What I learned:

What confused me at first:

How this connects to SOC Level 1 work:

What I want to learn next:

---

## 8. Skills Demonstrated

- Social engineering risk analysis
- Phishing detection mindset
- SOC investigation thinking
- Security awareness
- Incident response basics
- Defensive documentation