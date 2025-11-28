# 1️⃣ Introduction

**Tester(s):**  
- Name: Santeri Saari 

**Purpose:**  
- The purpose of this test was to pinpoint vulnerabilities in the sites user registration process.

**Scope:**  
- Tested components: User Registration process
- Exclusions: All else
- Test approach: Gray-box

**Test environment & dates:**  
- Start: 24.11.1025
- End: 28.11.2025
- Test environment details: Kali Linux VM, using Docker Engine. Chromium browser via Burp Suite.

**Assumptions & constraints:**  
- Multiple days of access time, no credentials provided

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences): Multiple vulnerabilities found, ranging from minor to major issues.

**Overall risk level:** High

**Top 5 immediate actions:**  
1.  Investigate password field input sanitization
2.  Enforce proper password requirements
3.  Add CSP header
4.  Add missing Anti-CSRF tags
5.  Obfuscate the password in site responses

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
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
| F-01 | 🔴 High | Potential SQL injection | Password field doesnt sanitize input, accepting SQL syntax as a password |  |
| F-02 | 🟠 Medium | Missing CSRF tokens | No CSRF tokens in HTTP headers  | <form action="/register" method="POST"> |
| F-03 | 🟠 Medium | Missing CSP headers | Session ID remains unchanged after login | Method: `GET` |
| F-04 | 🟡 Low | Vulnerable password in response | Shows passwords as plaintext in site responses |  |
| F-05 | 🟡 Low | Weak password policy | Has no rules for passwords, accepts even single characters |  |



---

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
