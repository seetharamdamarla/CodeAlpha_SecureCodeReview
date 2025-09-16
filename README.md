# Secure Coding Review — Password Security Tool

## Overview
This repository contains the secure coding review report for the **Password Security Tool** project.  
The tool is a Python-based CLI application that interacts with sensitive data, such as user-provided passwords.  
Because of its scope, a secure coding review was conducted to identify potential risks and provide remediation steps.

## Report Contents
The report includes:
- Executive Summary  
- Findings (issues and risks)  
- Concrete remediation plan and code patches  
- CI/CD integration recommendations  
- Testing recommendations  
- Tools and commands for static analysis and dependency checks  

## Key Findings
The review highlights several common security issues:
1. Passwords printed to console or logs  
2. Plaintext storage of sensitive data  
3. Weak or incorrect use of hashing algorithms  
4. Hard-coded secrets or credentials in source code  
5. Insecure dependency versions and supply-chain risks  
6. Unhandled exceptions leaking stack traces  
7. Unsafe subprocess or shell usage with user input  

## Recommendations
- Replace `input()` with `getpass.getpass()` for secure password entry  
- Use Argon2 (via `argon2-cffi`) for password hashing  
- Avoid plaintext storage of sensitive data  
- Remove hardcoded secrets and use environment variables  
- Run dependency scans using `pip-audit` or `safety`  
- Add static analysis tools such as `bandit`  
- Integrate CI/CD workflows for automated security checks  

## Deliverable
The main deliverable is the PDF report:  
**`PasswordSecurityTool_Review.pdf`**

This document summarizes the findings, risks, and remediation steps for the Password Security Tool project.
