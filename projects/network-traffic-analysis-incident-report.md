# Network Traffic Analysis Incident Report

## Overview

This report documents a simulated website compromise investigation from my SOC Level 1 learning. The goal of this activity was to analyze network traffic, identify relevant protocols, document the incident, and recommend preventions for the identified attack.

## Incident Documentation

Multiple customers contacted yummyrecipesforme's helpdesk complaining that the website prompted them to download a file to access free recipes. Customers also have reported that their computers ran slowly after running the file. The admin/website owner tried to log into their website but was locked out of their respective account.

## Evidence Reviewed

| Evidence Source | Purpose |
|---|---|
| tcpdump traffic log | Used to identify network activity and protocols involved |
| Sandbox test | Used to observe the suspicious website behavior safely |
| Customer reports | Used to understand how users discovered the issue |
| Source code review | Used to confirm unauthorized JavaScript modification |
| Malware/script analysis | Used to confirm browser redirection behavior |

## Network Protocol Analysis

The tcpdump log shows the browser first sent a DNS request for `yummyrecipesforme.com`. 203.0.113.22 was returned by the DNS server.Afterwards, the browser established a three-way TCP handshake with the website over port 80. Then, the browser sent an HTTP GET request for the homepage.

The traffic log showed that there was additional HTTP traffic over port 80. Based on this scenario, the user was then prompted to download and run an executable file. Later, the tcpdump log showed that the browser sent an additional DNS request for `greatrecipesforme`.com and received IP address 192.0.2.17. The browser then established another three-way TCP handshake with `greatrecipesforme.com` over port 80 and an HTTP GET request was sent to that domain.

This sequence indicates that the user first accessed the legitimate website,`yummyrecipesforme.com`, and was later redirected to a different domain,`greatrecipesforme.com`. This domain change is the key suspicious indicator.

## Incident Timeline

| Step | Time | Event |
|---|---|---|
| 1 | 14:18:32 | DNS request sent for `yummyrecipesforme.com` |
| 2 | 14:18:32 | DNS returned `203.0.113.22` for `yummyrecipesforme.com` |
| 3 | 14:18:36 | TCP three-way handshake established with `yummyrecipesforme.com` over HTTP/port 80 |
| 4 | 14:18:36 | Browser sent an HTTP `GET /` request to load the homepage of `yummyrecipesforme.com` |
| 5 | After 14:18:36 | Additional HTTP traffic occurred over port 80, consistent with the webpage loading and the suspicious download behavior described in the scenario |
| 6 | 14:20:32 | DNS request sent for `greatrecipesforme.com` |
| 7 | 14:20:32 | DNS returned `192.0.2.17` for `greatrecipesforme.com` |
| 8 | 14:25:29 | TCP three-way handshake established with `greatrecipesforme.com` over HTTP/port 80 |
| 9 | 14:25:29 | Browser sent an HTTP `GET /` request to load the homepage of `greatrecipesforme.com` |

## Root Cause

The primary root cause of the incident was weak administrative access control. The attacker was able to gain control and access admin panel through a brute-force attack because the administrative account was still using a default password. There were no effective controls placed to limit repeated login attempts, such as account lockout, rate limiting, or multi-factor authentication.

After gaining access, the attacker modified the website source code and added a malicious JavaScript that prompted the visitor to download and run an executable file. This redirected users from the legitimate website, `yummyrecipesforme.com`, to the suspicious domain `greatrecipesforme.com`.

## Impact

The incident affected the integrity of `yummyrecipesforme.com` because unauthorized changes were made to the website's source code. Website visitors were exposed to a suspicious executable download file, and were redirected to `greatrecipesforme.com`, a fake website associated to malware. The website owner was also not able to access the admin panel after the attacker changed the administrative password during the compromise.
 
## Recommendation

### Recommended Control

1. Implement login rate limiting or account lockout for administrative accounts.
2. Disallow usage of previous passwords and have frequent password updates.
3. Implement two-factor authentication (2FA)

### Why This Helps

The root cause that allowed the attacker to gain control of the system was the use of default passwords. Thus, having stricter password measures will make sure that any malicious actor that attempt a brute force attack will not likely gain access to the system because it will require additional authentication and limited attempts.

## Lessons Learned

- Default or weak administrative passwords create a major security risk
- Brute-force attacks can be reduced by using controls and applying security hardening techniques.
- Network traffic analysis can help reconstruct an incident by showing DNS lookups, TCP connections, and HTTP traffic.