# CyberRange Vulnerability Lab

This CyberRange simulates a vulnerable web application where 10 common security vulnerabilities have been identified and mitigated. It serves as a hands-on environment for learning about web application security and understanding how to exploit and patch real-world vulnerabilities.

## 🛡️ Vulnerabilities Covered

The lab covers the following vulnerabilities:

- **Cross-Site Scripting (XSS)**: Found in feedback and username fields.
- **Improper Authorization**: Admin users were able to delete other admins.
- **Directory Traversal**: Exploitable through file and attachment downloads.
- **Insecure Password Practices**: Weak password strength enforcement.
- **OTP Bypass**: Exploitable due to predictable OTP length.
- **Identity Spoofing**: Users could impersonate others by changing their display name.
- **Multiple Submissions**: Labs could be submitted more than once.
- **Game Logic Flaw**: Challenges could be submitted with negative scores.

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- **Go** (tested with Go 1.x)
- **Node.js** and **npm** (or alternatives like `pnpm`, `yarn`, or `bun`)

### Backend Setup

1. Navigate to the `backend` directory.
2. Run the backend server:

```bash
go run .
