# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** | Comment |
| :----: | :--- | :--- |
| &nbsp;✅&nbsp; | Have all personal data collected and processed in the system been<br> identified? (e.g., name, email, age, username) |
| &nbsp;⚠️&nbsp; | Have you ensured that only necessary personal data is collected (data minimization)? | Birthday vs. age |
| &nbsp;✅&nbsp; | Is user age recorded to verify that the booker is over 15 years old? |

---

| **Result** | **User registration and management** | Comment |
| :----: | :--- | :--- |
| &nbsp;⚠️&nbsp; | Does the registration form (page) include GDPR-compliant consent for processing<br> personal data (e.g., acceptance of the privacy policy)?| x |
| &nbsp;⚠️&nbsp; | Can users view, edit, and delete their own personal data via their account? | x |
| &nbsp;❌&nbsp; | Is there a mechanism for the administrator to delete a reserver in<br> accordance with the "right to be forgotten"? | x |
| &nbsp;✅&nbsp; | Is underage registration (under 15 years) and booking functionality restricted? |

---

| **Result** | **Booking visibility** | Comment |
| :----: | :--- | :--- |
| &nbsp;✅&nbsp; | Are bookings visible to non-logged-in users only at the resource level<br> (without any personal data)? |
| &nbsp;⚠️&nbsp; | Is it ensured that names, emails, or other personal data of bookers are not exposed<br> publicly or to unauthorized users? | x |

--- 

| **Result** | **Access control and authorization** | Comment |
| :----: | :--- | :--- |
| &nbsp;❌&nbsp; | Have you ensured that only administrators can add, modify, and delete<br> resources and bookings? | x |
| &nbsp;✅&nbsp; | Is the system using role-based access control (e.g., reserver vs. administrator)? |
| &nbsp;✅&nbsp; | Are administrator privileges limited to ensure GDPR compliance (e.g., administrators<br> cannot use data for unauthorized purposes)? |

---

| **Result** | **Privacy by Design Principles** | Comment |
| :----: | :--- |
| &nbsp;⚠️&nbsp; | Has Privacy by Default been implemented (e.g., collecting the minimum data by default)? | x |
| &nbsp;⚠️&nbsp; | Are logs implemented without unnecessarily storing personal data? | x |
| &nbsp;❌&nbsp; | Are forms and system components designed with data protection in mind<br> (e.g., secured login, minimal fields)? |

---

| **Result** | **Data security** | Comment |
| :----: | :--- | :--- |
| &nbsp;✅&nbsp; | Are CSRF, XSS, and SQL injection protections implemented? |
| &nbsp;✅&nbsp; | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)? |
| &nbsp;❌&nbsp; | Are data backup and recovery processes GDPR-compliant? | x |
| &nbsp;❌&nbsp; | Is personal data stored in data centers located within the EU? | x |

---

| **Result** | **Data anonymization and pseudonymization** | Comment |
| :----: | :--- | :--- |
| &nbsp;❌&nbsp; | Is personal data anonymized where possible? | x |
| &nbsp;✅&nbsp; | Are pseudonymization techniques used to protect data while maintaining its utility? |

---

| **Result** | **Data subject rights** | Comment |
| :----: | :--- | :--- |
| &nbsp;❌&nbsp; | Can users download or request all personal data related to them (data access request)? | x |
| &nbsp;❌&nbsp; | Is there an interface or process for users to request the deletion of their personal data? | x |
| &nbsp;❌&nbsp; | Can users withdraw their consent for data processing? | x |

---

| **Result** | **Documentation and communication** | Comment |
| :----: | :--- | :--- |
| &nbsp;❌&nbsp; | Is there a privacy policy available to users during registration and easily accessible? | x |
| &nbsp;❌&nbsp; | Are administrators and developers provided with documented data protection practices <br>and processing activities? | x |
| &nbsp;❌&nbsp; | Is there a documented data breach response process (e.g., how to notify authorities <br>and users of a breach)? | x |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)
