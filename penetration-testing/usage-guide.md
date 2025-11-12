# PenTestGPT (Web Apps & APIs) - Usage Guide

## What It Does

A professional, ethical pentesting copilot for web applications and APIs. Helps plan, execute, and analyze authorized security testing with a focus on practical, reproducible techniques.

---

## ⚠️ IMPORTANT: Authorized Testing Only

This GPT is designed for **AUTHORIZED penetration testing only**:
- Explicit written permission
- Bug bounty programs (in-scope only)
- Personal lab environments
- Authorized security assessments

**Unauthorized testing is illegal.**

---

## Setup

### ChatGPT
1. Go to https://chat.openai.com
2. Click your profile → "My GPTs" → "Create a GPT"
3. Click "Configure"
4. Fill in:
   - **Name**: `PenTestGPT`
   - **Description**: `Professional pentesting copilot for web applications and APIs. Provides practical, ethical security testing guidance with safe, reproducible techniques.`
   - **Instructions**: Copy everything from [instructions.txt](./instructions.txt)
5. Click "Save"

### Claude
1. Create a new Project
2. Copy everything from [instructions.txt](./instructions.txt)
3. Paste into "Project knowledge"

---

## How to Use

### Recon & Planning
```
I need to test [target-domain]. Help me plan the reconnaissance phase.
```

### Web App Testing
```
I found a login form at /admin. How do I test for SQL injection safely?
```

### API Testing
```
Analyze this JWT token and suggest authentication bypass techniques
```

### Generate PoC
```
Create a safe XSS proof-of-concept that demonstrates the vulnerability without harm
```

### Reporting
```
Generate a professional write-up for the IDOR vulnerability I found
```

---

## What It Covers

### Web Application Testing
- XSS (Reflected, Stored, DOM-based)
- SQL Injection
- SSRF
- CSRF
- Open Redirect
- Template Injection
- Command Injection (non-destructive)
- IDOR/BOLA
- LFI/RFI (safe testing)
- File Upload vulnerabilities
- Business logic flaws

### API Security
- Authentication/Authorization flows
- JWT/JWE/JWS analysis
- Rate limiting bypass
- Object-level authorization
- Mass assignment
- JSON/XML injection
- REST API testing
- GraphQL introspection and testing
- API schema analysis

### Reconnaissance
- Subdomain enumeration
- Technology fingerprinting
- Endpoint discovery
- Asset mapping

### Analysis & Reporting
- HTTP traffic interpretation
- Burp Suite log analysis
- Safe PoC generation
- OWASP/CWE mapping
- Professional write-ups

---

## Output Format

Every response includes:

1. **Context Recap** - What we know
2. **Assumptions & Scope Check** - Authorization verification
3. **Goals** - What we're testing
4. **Step-by-Step Plan** - CLI and/or Burp workflow
5. **Safe Payloads** - Non-destructive test inputs
6. **What to Observe** - Expected vs. questionable behavior
7. **Triage & Next Steps** - Analysis and recommendations
8. **Mitigations** - How to fix

---

## Common Use Cases

**Test for SQL Injection:**
```
How do I test this login endpoint for SQL injection using safe payloads?
```

**Analyze API Authentication:**
```
Here's a JWT token from the API. Analyze it for security issues.
```

**Subdomain Discovery:**
```
Help me discover subdomains for [domain] using passive and active techniques.
```

**Test File Upload:**
```
The app has a file upload feature. What security tests should I perform?
```

**GraphQL Testing:**
```
I found a GraphQL endpoint. How do I test for introspection and query flaws?
```

**Generate Report:**
```
Create a professional finding report for the XSS vulnerability in the search parameter.
```

---

## Safety Features

✅ **Non-Destructive Testing**
- Only safe, reversible test payloads
- Read-only verification techniques
- Proof-by-observation approach

✅ **Authorization Checks**
- Always verifies scope before providing guidance
- Refuses unauthorized testing requests
- Emphasizes legal and ethical boundaries

✅ **Self-Check Framework**
Before each response, verifies:
1. Is request in authorized scope?
2. Are steps non-destructive?
3. Is reasoning reproducible?
4. Are we guiding verification, not exploitation?

---

## Tools Integration

Works with:
- **Burp Suite** (Professional/Community)
- **curl** and command-line tools
- **Browser DevTools**
- **Postman/Insomnia** (API testing)
- **Custom scripts** (Python, Bash)

Provides both GUI (Burp) and CLI workflows when applicable.

---

## Best Practices

✅ **Do:**
- Verify authorization before testing
- Use safe, non-destructive payloads
- Document all findings thoroughly
- Follow responsible disclosure
- Test in lab environments first

❌ **Don't:**
- Test without authorization
- Use destructive payloads
- Exfiltrate real data
- Deploy malware or backdoors
- Skip documentation

---

## Example Session

**User:** I found a search parameter that might be vulnerable to XSS. How do I test it safely?

**GPT Response Format:**

**Context Recap:**
Testing search parameter for XSS

**Assumptions & Scope Check:**
- Assuming you have authorization to test this application
- Target: search parameter in web application

**Goals:**
- Verify if search parameter reflects unsanitized input
- Test for XSS without causing harm

**Step-by-Step Plan:**
1. Test with benign reflection payload
2. Test with HTML injection
3. Test with safe JavaScript (alert with unique string)
4. Verify CSP and other protections

**Safe Payloads:**
```
<script>console.log('XSS-TEST-12345')</script>
<img src=x onerror=console.log('XSS')>
```

[... continues with full analysis ...]

---

## Limitations

- Focuses on web apps and APIs (not network/infrastructure)
- Provides guidance, not automated exploitation
- Requires professional security knowledge
- Cannot execute actual tests
- Always verify in safe environment first

---

## Questions?

Create an issue in the repo or reach out to the maintainers.
