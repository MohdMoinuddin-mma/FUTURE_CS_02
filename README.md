# FUTURE_CS_02 — Phishing Email Detection & Awareness System

**Future Interns | Cyber Security Internship Programme 2026**

---

## 👤 Intern Details

| Field | Details |
|---|---|
| **Name** | Mohammad Moinuddin |
| **CIN ID** | FIT/FEB26/CS6460 |
| **Track** | Cyber Security |
| **Task** | Task 2 — Phishing Email Detection & Awareness System |
| **Date** | March 2026 |

---

## 📋 Task Overview

This task involved analysing real-world phishing email samples, identifying 
common phishing indicators, classifying email risk, and creating a professional 
awareness report that businesses and employees can use to protect themselves 
from phishing attacks.

---

## 🎯 Objective

- Analyse real phishing email samples across multiple attack categories
- Identify phishing indicators using technical tools
- Classify emails by risk level (Safe / Suspicious / Phishing)
- Explain attacks in simple, business-friendly language
- Create prevention guidelines for employees

---

## 📧 Phishing Samples Analysed

| # | Type | Brand Impersonated | Sender Domain | Risk |
|---|---|---|---|---|
| 1 | Financial Fraud | PayPal | paypaypal[.]net | 🔴 HIGH |
| 2 | Delivery Scam | Canada Post | webnotifications[.]net | 🔴 HIGH |
| 3 | Social Media Takeover | Instagram (Meta) | webnotifications[.]net | 🔴 HIGH |
| 4 | IT/Corporate Phishing | Microsoft | access-accsecurity[.]com | 🔴 HIGH |
| 5 | Banking Fraud | Royal Bank of Canada | RoyalBanlOfCannada@hotmail[.]com | 🔴 HIGH |

> ⚠️ **Key Finding:** Samples 2 and 3 share the same fake domain 
> (`webnotifications[.]net`) and the same AWS IP address, confirming 
> a coordinated multi-brand campaign by a single threat actor.

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Google Admin Toolbox — Message Header Analyzer | Parse email headers, extract SPF/DKIM/DMARC results |
| MXToolbox SuperTool | Domain MX lookup, DMARC check, DNS verification |
| MXToolbox Blacklist Check | Check IPs/domains against 61–70 spam blacklists |
| Browser DevTools | Inspect redirect chains and phishing login pages |
| Canva | Annotate screenshots with red-flag indicators |
| GitHub — rf-peixoto/phishing_pot | Source of real-world .eml phishing samples |

---

## 🔍 Methodology

This assessment followed a **strictly read-only, passive analysis scope**:

- ✅ Public-facing email sample analysis only
- ✅ Passive header scanning
- ✅ Domain reputation checks
- ✅ Authentication record verification (SPF, DKIM, DMARC)
- ❌ No exploitation or login bypass attempts
- ❌ No active attacks or link activation
- ❌ No denial-of-service or brute force

---

## 📊 Key Technical Findings

### Authentication Results
| Sample | SPF | DKIM | DMARC | Blacklisted |
|---|---|---|---|---|
| PayPal | ❌ None | ❌ None | ❌ None | — |
| Canada Post | ❌ None | ❌ None | ❌ None | — |
| Instagram | ❌ None | ❌ None | ❌ None | — |
| Microsoft | ❌ None | ❌ None | 🟠 Permerror | — |
| Royal Bank | 🟠 Softfail | ❌ None | 🔴 Fail | ✅ LISTED |

### Notable Findings
- **Zero authentication** — Not a single phishing email passed SPF, DKIM, or DMARC
- **Blacklisted server** — Royal Bank sending server (`oblszn57.ru`) confirmed on UCEPROTECTL3
- **Ghost domains** — `access-accsecurity.com` and `thcultarfdes.co.uk` have no DNS records
- **Shared infrastructure** — Canada Post & Instagram phishing used identical attack servers

---

## 📁 Repository Structure
```
FUTURE_CS_02/
├── README.md
├── Report/
│   └── Phishing_Awareness_Report_Mohammad_Moinuddin.pdf
├── Evidence/
│   ├── 01_PayPal_Email_Annotated.png
│   ├── 02_PayPal_Email_Part2_Annotated.png
│   ├── 03_PayPal_FakeLogin.png
│   ├── 04_CanadaPost_Email_Annotated.png
│   ├── 05_CanadaPost_Email_Part2_Annotated.png
│   ├── 06_CanadaPost_FakeLogin.png
│   ├── 07_Instagram_Email_Annotated.png
│   ├── 08_Instagram_FakeLogin.png
│   ├── 09_Microsoft_HeaderAnalysis.png
│   ├── 10_RoyalBank_HeaderAnalysis.png
│   ├── 11_MXToolbox_paypaypal.png
│   ├── 12_MXToolbox_webnotifications.png
│   ├── 13_MXToolbox_access-accsecurity.png
│   ├── 14_MXToolbox_thcultarfdes.png
│   ├── 15_MXToolbox_oblszn57.png
│   ├── 16_Blacklist_IP_Check.png
│   └── 17_Blacklist_Domain_Check.png
```

---

## 🛡️ Prevention Guidelines Summary

1. Always check the actual sender email address — not just the display name
2. Never click links under urgency pressure — go directly to official websites
3. Check for grammar and spelling errors in emails claiming to be from brands
4. Verify unusual financial requests independently by calling the organisation
5. Enable Multi-Factor Authentication (MFA) on all critical accounts
6. Report suspicious emails to your IT/security team immediately

---

## 📚 References

- [Google Admin Toolbox](https://toolbox.googleapps.com/apps/messageheader/)
- [MXToolbox SuperTool](https://mxtoolbox.com/SuperTool.aspx)
- [rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot)
- [OWASP Phishing Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Phishing_Prevention_Cheat_Sheet.html)
- [Future Interns LinkedIn](https://www.linkedin.com/company/future-interns)

---

> *This project was completed as part of the Future Interns Cyber Security 
> Internship Programme 2026. All analysis was conducted ethically and within 
> a defined read-only scope. No systems were compromised or harmed.*
