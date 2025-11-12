# Security JIRA Ticket Generator - Usage Guide

## What It Does

Converts vulnerability findings into structured JIRA tickets automatically.

---

## Setup

### ChatGPT
1. Go to https://chat.openai.com
2. Click your profile → "My GPTs" → "Create a GPT"
3. Click "Configure"
4. Fill in:
   - **Name**: `JIRATicketGPT`
   - **Description**: `Generates structured JIRA tickets for security vulnerabilities from scanner outputs, CVEs, and security findings.`
   - **Instructions**: Copy everything from [instructions.txt](./instructions.txt)
5. Click "Save"

### Claude
1. Create a new Project
2. Copy everything from [instructions.txt](./instructions.txt)
3. Paste into "Project knowledge"

---

## How to Use

Simply paste your vulnerability data:

```
HIGH spring-security-crypto 5.8.16 CVE-2025-22228
```

Or:

```
Generate a JIRA ticket for CVE-2025-22228
```

---

## Supported Input Formats

**Simple CVE:**
```
HIGH spring-security-crypto 5.8.16 CVE-2025-22228
```

**Scanner Output:**
```
HIGH /path/pom.xml org.springframework.security:spring-security-crypto 5.8.16 -> 5.8.18 CVE-2025-22228
CVSS: 8.1
```

**CSV:**
```
Severity,Package,Current,Fixed,CVE
HIGH,spring-security-crypto,5.8.16,5.8.18,CVE-2025-22228
```

**JSON:**
```json
{
  "severity": "HIGH",
  "package": "spring-security-crypto",
  "version": "5.8.16",
  "cve": "CVE-2025-22228"
}
```

**Free Text:**
```
We found a high severity issue in spring-security-crypto version 5.8.16.
It should be upgraded to 5.8.18. CVE-2025-22228.
```

**Code Vulnerabilities:**
```
SonarQube: SQL Injection in UserController.java line 145
Severity: Critical
CWE-89
```

---

## Supported Scanners

Works with outputs from:
- Snyk
- Dependabot
- Wiz
- Cycode
- SonarQube
- npm audit
- pip-audit
- Trivy
- OWASP Dependency Check
- GitHub Security Advisories

---

## Common Commands

**Single vulnerability:**
```
Generate a JIRA ticket for CVE-2025-22228
```

**Batch processing:**
```
Generate JIRA tickets for:
- HIGH spring-security-crypto 5.8.16 CVE-2025-22228
- CRITICAL jackson-databind 2.12.1 CVE-2022-42003
- MEDIUM lodash 4.17.20 CVE-2021-23337
```

**Custom fields:**
```
Generate a ticket for CVE-2025-22228 and include:
- Team: Platform Team
- Sprint: Q4 Security
```

**Custom severity scale:**
```
Use our severity scale: Critical = customer data at risk
```

---

## Output Format

You'll receive a complete JIRA ticket with:
- **Summary** - Concise title
- **Description** - What the vulnerability is
- **Severity & CVSS Score** - Risk level
- **CVE ID & Issue URL** - References
- **Affected Components** - What's impacted
- **Impact** - Security risks
- **Recommendation** - How to fix
- **References** - Links to documentation
- **Labels** - For categorization
- **Priority & Due Date** - Based on severity
- **Acceptance Criteria** - Checklist for completion

---

## Tips

✅ Review GPT output before creating tickets  
✅ Sanitize data (remove credentials, API keys, paths)  
✅ Verify CVE details  
✅ Customize for your organization  
✅ Batch process multiple vulnerabilities  

❌ Don't paste sensitive production data  
❌ Don't skip verification of remediation steps  
❌ Don't blindly accept all recommendations  

---

## Troubleshooting

**Issue:** GPT not following format  
**Fix:** Say "Please use the exact ticket format specified"

**Issue:** Missing information  
**Fix:** Provide more details (CVSS score, affected files, etc.)

**Issue:** Need subtasks  
**Fix:** Ask "Generate with subtasks for each affected module"

---

## Questions?

Create an issue in the repo or reach out to the maintainers.
