# Secure Code Reviewer - Usage Guide

## What It Does

Reviews application code for security vulnerabilities and provides secure rewrites with actionable remediation guidance.

---

## Setup

### ChatGPT
1. Go to https://chat.openai.com
2. Click your profile → "My GPTs" → "Create a GPT"
3. Click "Configure"
4. Fill in:
   - **Name**: `CodeSecGPT`
   - **Description**: `Reviews application code for security vulnerabilities and provides secure rewrites aligned with OWASP best practices.`
   - **Instructions**: Copy everything from [instructions.txt](./instructions.txt)
5. Click "Save"

### Claude
1. Create a new Project
2. Copy everything from [instructions.txt](./instructions.txt)
3. Paste into "Project knowledge"

---

## How to Use

Simply paste your code and ask for a review:

```python
def login(username, password):
    query = "SELECT * FROM users WHERE username='" + username + "'"
    return db.execute(query)
```

Or:

```
Review this code for security issues
```

---

## What It Reviews

**Vulnerability Classes:**
- Injection (SQL, Command, LDAP, XML)
- XSS and CSRF
- Weak cryptography
- Authentication & authorization issues
- Path traversal
- Hardcoded credentials
- Insecure deserialization
- Input/output validation issues

**Severity Levels:**
- Critical: System compromise, RCE, SQL injection
- High: XSS, CSRF, weak crypto, auth bypass
- Medium: Information disclosure, weak validation
- Low: Minor improvements, defense-in-depth
- Informational: Best practice recommendations

---

## Common Commands

**Basic review:**
```
Review this code for security issues
```

**Request unit tests:**
```
Review this code and include unit tests for the secure fixes
```

**Focus on specific vulnerability:**
```
Check this code specifically for SQL injection vulnerabilities
```

**Framework context:**
```
I'm using Django - review this view for security issues
```

**Iterative review:**
```
I fixed the SQL injection. Review the updated code for any remaining issues.
```

---

## Output Format

You'll receive:
- **Finding** - What the vulnerability is
- **Exploit Example** - How it could be exploited
- **Secure Rewrite** - Fixed code
- **Justification** - Why the fix works
- **Preventive Guidance** - How to avoid similar issues
- **Remediation Priority** - Order to fix issues

---

## Tips

✅ Paste complete code snippets with context  
✅ Specify framework/library versions you're using  
✅ Iterate until all vulnerabilities are fixed  
✅ Request unit tests when you need them  

❌ Don't paste production credentials or API keys  
❌ Don't assume the first pass caught everything  
❌ Don't skip testing the secure rewrites  

---

## Supported Languages

Python, JavaScript/TypeScript, Java, C#, Go, PHP, Ruby, Rust, C/C++, Kotlin, Swift, and others.

---

## Limitations

- Reviews code you paste (not entire codebases)
- Focuses on security, not general code quality
- Requires context for framework-specific issues

Always use in addition to automated scanners and peer review.

---

## Questions?

Create an issue in the repo or reach out to the maintainers.
