# 1️⃣ Introduction

**Tester(s):**  
- Kati Asmundi  

**Purpose:**  
- The purpose of this penetration test was to identify security vulnerabilities in the BookingSystem Phase 1 registration flow, focusing specifically on authentication and input validation.

**Scope:**  
- Tested components: Registration page (/register), Registration POST endpoint, UI validation mechanisms, Server-side request handling, Automated ZAP baseline scan
- Exclusions:  Login functionality etc.
- Test approach: Gray-box

**Test environment & dates:**  
- Start:  17.11.2025
- End:  22.11.2025
- Test environment details (OS, runtime, DB, browsers): Windows OS, ZAP, Postgres, Mozilla Firefox

**Assumptions & constraints:**  
- Limited time and only registration was in scope.

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  

**Overall risk level:** Medium

**Top 5 immediate actions:**  
1.  Implement Anti-CSRF tokens on all POST forms
2. Add critical security headers: CSP, X-Frame-Options, X-Content-Type-Options
3. Fix the server error (HTTP 500) when invalid data is submitted
4. Strengthen input validation to prevent malformed email injection attempts
5. Add consistent error handling to avoid information disclosure

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings (filled with examples → replace)

> Fill in one row per finding. Focus on clarity and the most important issues.

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | SQL Injection in registration | Input field allows `' OR '1'='1` injection | Screenshot or sqlmap result |
| F-02 | 🟠 Medium | Session fixation | Session ID remains unchanged after login | Burp log or response headers |
| F-03 | 🟡 Low | Weak password policy | Accepts passwords like "12345" | Screenshot of registration success |

| F-01 | 🔴 High | Unrestricted Administrator Registration | The registration form allows users to select the “administrator” role directly from the dropdown menu. This enables any unauthenticated user to create a full-privilege admin account without restriction. This is a design-level flaw leading to complete system compromise. | <img width="485" height="140" alt="image" src="https://github.com/user-attachments/assets/2b6cf0bb-1d56-4350-a47e-0981726de066" /> |
| F-02 | 🔴 High |  |  |  |
| F-03 | 🔴 High |  |  |  |
| F-04 | 🔴 High |  |  |  |
| F-05 | 🔴 High |  |  |  |
| F-06 | 🔴 High |  |  |  |
| F-07 | 🔴 High |  |  |  |
| F-08 | 🔴 High |  |  |  |
| F-09 | 🔴 High |  |  |  |

F-01	🔴 High	Role Manipulation / Privilege Escalation	The role field is not validated server-side, allowing a user to register as an administrator.	DB record: user_id 32 → role = administrator
F-02	🔴 High	Missing Server-Side Input Validation	Application accepts invalid, empty, and malformed values in all fields (email, password, birthdate, role), enabling multiple attack vectors.	DB entries: empty username, invalid emails (test@, asdfgh), invalid birthdates
F-03	🔴 High	Stored XSS (payload stored in DB)	Harmful JavaScript is stored in the database and will execute once rendered in any future view (e.g., admin panel).	DB: test<script>alert(1)</script>@mail.com
F-04	🟠 Medium	Weak Password Policy	System accepts extremely weak and even empty passwords, allowing trivial account takeover.	DB examples: "", "a", "123", "i"
F-05	🟠 Medium	SQL Injection Payload Accepted	SQLi strings are stored in the database, indicating missing sanitization, even though no execution occurred.	DB: test@example.com' OR 1=1 --
F-06	🟠 Medium	No CSRF Protection	Registration form contains no anti-CSRF token, enabling CSRF attacks.	ZAP: “Absence of Anti-CSRF Tokens”
F-07	🟠 Medium	Missing Security Headers	CSP, X-Frame-Options, and X-Content-Type-Options headers are missing, increasing XSS and clickjacking risk.	ZAP report (multiple instances)
F-08	🟡 Low	Server Error Disclosure	Submitting invalid input produces HTTP 500, leaking internal behavior.	ZAP: “Application Error Disclosure”
F-09	🟡 Low	Invalid Date and Age Handling	Birthdate validation is missing; underage users, future dates, and nonsensical years are accepted.	DB: 0015-01-01, 2050-01-01, under-15 birthdates
---

> [!NOTE]
> Include up to 5 findings total.   
> Keep each description short and clear.

---

# 5️⃣ OWASP ZAP Test Report (Attachment)

**Purpose:**  
- Attach or link your OWASP ZAP scan results (Markdown format preferred).

---

**Instructions (CMD version):**
1. Run OWASP ZAP baseline scan:  
   ```bash
   zap-baseline.py -t https://example.com -r zap_report_round1.html -J zap_report.json
   ```
2. Export results to markdown:  
   ```bash
   zap-cli report -o zap_report_round1.md -f markdown
   ```
3. Save the report as `zap_report_round1.md` and link it below.

---
> [!NOTE]
> 📁 **Attach full report:** → `check itslearning` → **Add a link here**

---
