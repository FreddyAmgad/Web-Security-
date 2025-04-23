# 🔐 CyberRange Vulnerability Lab  
**A production-grade web application security sandbox with intentionally implemented and mitigated OWASP Top 10 vulnerabilities**

![Lab Architecture](https://img.shields.io/badge/Architecture-Microservices-9cf?logo=kubernetes&logoColor=white)
![Auth](https://img.shields.io/badge/Auth-JWT_%2B_Sessions-red?logo=openidconnect)
![Vulns](https://img.shields.io/badge/Vulnerabilities-10_Controlled_Exploits-orange?logo=owasp)

## 🎯 Lab Objectives
- Demonstrate **real-world exploit chains** using modern web attack vectors  
- Provide **patched equivalents** of all vulnerabilities for defensive training  
- Emulate **SDLC security gaps** through intentionally flawed commit history  

---

## 🧠 Vulnerability Matrix (CWE Mapped)

| Vulnerability Class          | Implementation Method          | Mitigation Strategy                     | CWE Reference |
|------------------------------|---------------------------------|-----------------------------------------|---------------|
| **Stored XSS**               | Unsanitized Markdown renderer  | CSP + DOMPurify (v3.0.5)                | CWE-79        |
| **Broken Access Control**    | Missing RBAC checks in Golang middleware | JWT claims validation + Session binding | CWE-862       |
| **Path Traversal**           | Unrestricted `filepath.Join()` | Sandboxed filesystem (gVisor)           | CWE-22        |
| **Weak Credential Policy**   | 6-char minimum password        | zxcvbn (score≥3) + Argon2id KDF         | CWE-521       |
| **OTP Predictability**       | 4-digit numeric-only tokens    | TOTP (RFC 6238) with 30s validity       | CWE-613       |
| **Session Hijacking**        | Non-rotating session cookies   | SameSite=Strict + HMAC-signed sessions   | CWE-384       |
| **Race Condition**           | Unsynchronized score updates   | PostgreSQL SKIP LOCKED                   | CWE-362       |
| **Business Logic Bypass**    | Client-side validation only    | Semantic checks in gRPC interceptors     | CWE-840       |

---

## ⚙️ Technical Stack Deep Dive

### **Attack Surface Components**
```mermaid
graph TD
    A[Frontend: Next.js 14] -->|gRPC-Web| B[Backend: Go 1.22]
    B --> C[Auth: Ory Hydra]
    B --> D[Database: PostgreSQL 16]
    D --> E[Audit: Triggers]
    B --> F[Sandbox: gVisor]
