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
1.  Investigate SQL injection in input fields
2.  Enforce proper password requirements
3.  Add CSP header
4.  Add missing Anti-CSRF tags
5.  Add Anti-Clickjacking measures

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
| F-01 | 🔴 High | SQL injection in username and password fields | ZAP report <img width="335" height="417" alt="k0SDI1T" src="https://github.com/user-attachments/assets/df70fed6-7b67-461e-9fbf-3c4164c8b068" /> |
| F-02 | 🔴 High | Path Traversal | Form allows path traversal | ZAP report |
| F-03 | 🟠 Medium | Missing CSRF tokens | No CSRF tokens in HTTP headers  | ZAP report |
| F-04 | 🟠 Medium | Missing CSP headers | Missing CSP tokens in headers | ZAP report |
| F-05 | 🟡 Low | Missing Clickjacking header  | Missing Anti-Clickjacking headers | ZAP report |
| F-06 | 🟡 Low | Weak password policy | Has no rules for passwords, accepts even single characters | <img width="950" height="897" alt="sso53WH" src="https://github.com/user-attachments/assets/ac1ae019-c4b5-4f86-a6ee-655ec301f1e4" /> |



---

---

# 5️⃣ OWASP ZAP Test Report (Attachment)

---
> [!NOTE]
> [zap_report.md](https://github.com/user-attachments/files/23829463/zap_report_round1.md)

---

