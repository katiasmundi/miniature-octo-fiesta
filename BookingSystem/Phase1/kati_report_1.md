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

**Short summary (1-2 sentences):** The penetration test of the BookingSystem Phase 1 registration functionality revealed several significant security weaknesses, including a critical design flaw that allows any user to register as an administrator. In addition, missing input validation, insufficient security headers, stored XSS risks, and weak password handling substantially increase the overall attack surface.

**Overall risk level:** High

**Top 5 immediate actions:**  
1. Remove the administrator option from the public registration form and enforce server-side role validation.
2. Implement robust server-side input validation for email, password, birthdate, and role fields.
3. Introduce essential security headers (CSP, X-Frame-Options, X-Content-Type-Options) to reduce XSS and clickjacking risks.
4. Fix the HTTP 500 error handling to prevent information leakage and improve backend stability.
5. Strengthen password policy by enforcing minimum length and complexity requirements.

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
| F-01 | 🔴 High | Unrestricted Administrator Registration | The registration form allows users to select the “administrator” role directly from the dropdown menu. This enables any unauthenticated user to create a full-privilege admin account without restriction. This is a design-level flaw leading to complete system compromise. Also the role field is not validated server-side. | <img width="485" height="140" alt="image" src="https://github.com/user-attachments/assets/2b6cf0bb-1d56-4350-a47e-0981726de066" /> |
| F-02 | 🔴 High | Missing Server-Side Input Validation | All input fields (email, password, birthdate, role) accept invalid, empty, malformed and harmful values. This exposes the system to XSS, SQLi, data corruption, and privilege escalation. | <img width="722" height="422" alt="image" src="https://github.com/user-attachments/assets/339e5754-bddb-4e47-8241-dffd08f47a77" />
 |
| F-03 | 🔴 High | Stored XSS (payload stored in DB) | Malicious JavaScript is stored in the database and will execute when rendered in future views (e.g., admin user list). This indicates missing sanitization and output encoding. | test<script>alert(1)</script>@mail.com <img width="1074" height="188" alt="image" src="https://github.com/user-attachments/assets/db04beb5-a545-43ba-82e9-0d30ff2651aa" />
 |
| F-04 | 🟠 Medium | Weak Password Policy | Extremely weak passwords—1 character or even empty strings—are accepted. This allows trivial account guessing and significantly weakens authentication security. | "password", "123", "a", "" etc. <img width="1043" height="200" alt="image" src="https://github.com/user-attachments/assets/9a8047b9-9b89-4894-a4b6-2b788999deba" />
 |
| F-05 | 🟠 Medium | SQL Injection Payload Stored (Not Executed) | SQL injection strings are stored in plain form, showing that sanitization is missing. While no SQL execution occurred, this indicates a high risk for future exploitation. | test@example.com' OR 1=1 -- <img width="1080" height="206" alt="image" src="https://github.com/user-attachments/assets/9ec164bf-f318-4bc7-8754-d4bf7ac50c03" />
 |

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
