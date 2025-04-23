# CyberRange Vulnerability 

This project is the result of an advanced penetration testing initiative targeting a simulated **CyberRange** environment designed to emulate a real-world, enterprise-grade web application. As a team, we conducted a full-spectrum security audit leveraging both automated tools and manual exploitation techniques to uncover and analyze critical vulnerabilities in the system architecture.

We successfully identified and exploited **10+ high-impact security flaws**, ranging from client-side injection vectors to backend logic abuses and authentication bypasses. Each issue was thoroughly documented, exploited in a controlled environment, and mitigated through a combination of secure coding practices, access control refinements, and architectural hardening. This lab now serves as a fully patched, interactive learning platform for understanding the lifecycle of web application security threats—from reconnaissance and exploitation to remediation.

## 🔍 Vulnerabilities Identified & Mitigated

The lab includes real exploit scenarios for the following vulnerabilities:

- **Cross-Site Scripting (XSS)**: Persistent and reflected XSS vectors discovered in multiple input fields, leading to session hijacking.
- **Improper Authorization**: Privilege escalation via flawed access control logic allowed unauthorized user actions on high-privilege accounts.
- **Directory Traversal**: Arbitrary file read through unsanitized path parameters in download endpoints.
- **Weak Password Enforcement**: Lack of password complexity and rate-limiting exposed the platform to brute-force attacks.
- **One-Time Password (OTP) Bypass**: OTPs could be predicted and reused due to static generation logic and insufficient expiration handling.
- **User Impersonation**: Identity spoofing by manipulating profile attributes through insecure client-server communication.
- **Race Condition in Submissions**: Inconsistent state handling allowed users to submit labs multiple times, exploiting scoring logic.
- **Business Logic Flaw**: Vulnerable game challenge system permitted users to exploit negative scoring to manipulate leaderboards.

## 🚀 Getting Started

### Prerequisites

Ensure the following dependencies are installed:

- **Go** (version 1.x recommended)
- **Node.js** and **npm** (or `pnpm`, `yarn`, or `bun` as alternatives)

### Backend Setup

1. Navigate to the `backend` directory.
2. Run the server with:

```bash
go run .
