# cybersecurity-task-2-phishing-analysis

📧 Comprehensive Phishing Email Analysis Report

Internship Task 2 Submission  
Candidate: Abinesh S   
Date of Analysis: August 6, 2025  

🔍 Executive Summary

This document presents a comprehensive forensic analysis of a real-world phishing email impersonating a solar panel installer. The email exhibits multiple threat indicators including email spoofing, failed SPF verification, content-based social engineering, and URL redirection to potentially malicious tracking domains. This assessment provides both technical and behavioral analysis, as would be performed in a Security Operations Center (SOC) environment.


✉️ Email Metadata and Envelope Details

| Field               | Value                                                                 |
|--------------------|------------------------------------------------------------------------|
| From           | zonnepaneel@appjj.serenitepure.fr                                     |
| Reply-To       | news@aichakandisha.com                                                |
| Sender IP      | 57.128.69.202                                                         |
| Return-Path    | return@dturm.de                                                       |
| Subject        | =?UTF-8?B?8J+Uiw==?= Zonnepanelen voor een goede prijs                |
| Date           | Wed, 6 Augest 2025 04:56:15 +0000                                     |
| SPF Result     | None (unauthorized sender IP)                                         |
| Authentication | dkim=none, dmarc=none, compauth=fail                                  |


 🔎 Key Phishing Indicators

| Indicator                     | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| 1. Spoofed sender domain  | The domain `serenitepure.fr` is not associated with any known solar provider.   |
| 2. Reply-To mismatch    | Email replies are directed to `aichakandisha.com`, a completely unrelated domain. |
| 3. SPF authentication fail| SPF: none — the domain `dturm.de` did not authorize this IP.                    |
| 4. Suspicious URLs        | CTA links point to `go.nltrck.com`, a known tracking or phishing host.          |
| 5. Social engineering     | Uses urgency: "Wacht daarom niet langer..." (Don't wait any longer...)          |
| 6. Lack of personalization | No name, generic greeting, broad targeting language.                           |
| 7. Grammar issues         | Misspellings such as "aanbiederes" and broken Dutch syntax.                     |
| 8. Poor branding          | No logos, legitimate signatures, or verification badges.                        |



🧠 Behavioral & Content Analysis

The content is emotionally manipulative, targeting homeowners' anxiety about rising energy prices. It presents a false solution (solar panel offers) and directs users to click on a button leading to a third-party tracker:

> Link Preview:** `http://go.nltrck.com/?c=495&source=consumentenbond...`

The structure mimics legitimate marketing campaigns but lacks opt-out links, privacy notices, or proper regulatory compliance.


🧰 Threat Intelligence and IOC Summary

- Sender IP: 57.128.69.202  
- Suspicious Domain: `aichakandisha.com`  
- Tracking URL: `go.nltrck.com`  
- Failing Authentication: SPF, DKIM, DMARC all absent  

These indicators align with known tactics in phishing campaigns categorized under:  
- MITRE ATT&CK Technique T1566.001** – Phishing: Spearphishing via Email


Recommended Actions (SOC Perspective)

| Action Item                                 | Description                                                    |
|---------------------------------------------|--------------------------------------------------------------- |
| **Report and block sender IP**              | Add `57.128.69.202` to blocklists and alert threat intel feeds.|
| **Add domain to watchlist**                 | Monitor `aichakandisha.com` and `nltrck.com` in threat feeds.  |
| **Educate users on language red flags**     | Conduct phishing simulations using similar email structures.   |
| **Review URL redirect behavior**            | Analyze where `go.nltrck.com` redirects using safe browsing tools. |



🌐 Tools and Methodologies Used

- Manual Email Header Inspection  
- SPF/DKIM/DMARC Validation  
- WHOIS and DNS Lookups  
- Behavioral Analysis of Email Body  
- MITRE ATT&CK Mapping  
- URL Hover and Threat Intelligence Lookups  



📘 Conclusion

This email is a sophisticated example of phishing using low-fidelity spoofing and social engineering. While not overly complex, it exploits user trust and economic pressure to drive action. Detection required correlating technical metadata with behavioral cues. Proper security controls and employee training are critical to identifying and mitigating such threats.

Submission Prepared For: Cybersecurity Internship - Task 2  
Prepared By:** Abinesh S 
