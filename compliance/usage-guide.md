# ComplianceGPT - Usage Guide

A practical compliance assistant for security professionals working with SOC 2, ISO 27001, PCI-DSS, HIPAA, GDPR, and other frameworks.

---

## 🎯 What It Does

- Maps security controls to compliance frameworks
- Identifies compliance gaps and prioritizes remediation
- Guides evidence collection for audits
- Generates policies and procedures
- Provides audit-ready documentation

---

## 📋 How to Use

### 1. Copy Instructions to Your AI Assistant

Copy the contents of `instructions.txt` into:
- **ChatGPT**: Custom GPT instructions
- **Claude**: Project knowledge or system prompt
- **Other AI**: System instructions field

---

## 💬 Example Requests

### Control Mapping
```
Map multi-factor authentication to SOC 2, ISO 27001, and PCI-DSS requirements
```

```
How do I implement access control requirements for HIPAA?
```

### Gap Analysis
```
I need a SOC 2 gap analysis. Our current state:
- AWS environment
- GitHub for code
- Datadog for monitoring
- Annual access reviews
- No formal change management
```

```
Create a PCI-DSS compliance gap analysis for our e-commerce platform
```

### Evidence Collection
```
What evidence do I need for SOC 2 CC6.1 (Logical Access Controls)?
```

```
Create an evidence collection guide for ISO 27001 A.9.2.1 (User Registration)
```

### Policy Generation
```
Write an Incident Response Policy for ISO 27001 compliance
```

```
Generate an Access Control Policy that covers SOC 2 and HIPAA
```

### Remediation Planning
```
We're missing quarterly access reviews. How do we implement this for SOC 2?
```

```
Create a 90-day remediation roadmap for our SOC 2 critical gaps
```

---

## 🎓 Tips for Best Results

1. **Be Specific About Framework and Scope**
   - ✅ "SOC 2 Type II for our SaaS application"
   - ❌ "Compliance requirements"

2. **Provide Context**
   - Mention your tech stack (AWS, Azure, GCP, etc.)
   - Timeline (audit date if known)
   - Current state of controls

3. **Request Specific Outputs**
   - "Create an evidence collection guide"
   - "Map our controls to framework requirements"
   - "Generate a gap analysis with remediation plan"

4. **Iterate**
   - Start broad, then drill into specific controls
   - Ask follow-up questions for clarification
   - Request evidence examples if needed

---

## 🔧 Common Workflows

### Starting a New Compliance Program
1. "Create a SOC 2 readiness assessment plan"
2. "What are the critical controls I should implement first?"
3. "Generate a project timeline for SOC 2 certification"

### Preparing for an Audit
1. "List all evidence needed for SOC 2 Type II audit"
2. "Create evidence collection procedures for [specific control]"
3. "What will auditors look for in [specific area]?"

### Remediating Gaps
1. "We failed [control] in our audit. How do we remediate?"
2. "Provide implementation steps for [requirement]"
3. "What tools can automate [compliance activity]?"

### Policy Development
1. "Generate a [policy name] for [framework]"
2. "What sections are required in a [policy type]?"
3. "Review this policy against [framework] requirements"

---

## 📊 Output Types You'll Get

- **Control Mappings**: Framework requirements → Implementation steps → Evidence needed
- **Gap Analyses**: Current vs. required state → Prioritized remediation → Timelines
- **Evidence Guides**: What to collect → Where from → How to collect → Examples
- **Policies/Procedures**: Audit-ready documentation mapped to frameworks
- **Remediation Plans**: Step-by-step actions → Owners → Timelines → Resources

---

## ⚠️ Important Notes

- **Not Legal Advice**: ComplianceGPT provides technical guidance, not legal counsel
- **Verify with Auditors**: Always confirm interpretations with your auditor
- **Customize Outputs**: Adapt policies and procedures to your organization
- **Keep Updated**: Framework requirements change; verify you're using current versions
- **Context Matters**: Compliance requirements vary by industry and geography

---

## 🚀 Pro Tips

1. **Use for Multiple Frameworks**: "Map this control to SOC 2, ISO 27001, and PCI-DSS"
2. **Ask for Examples**: "Show me an example of acceptable evidence for this control"
3. **Get Timelines**: "How long will it take to implement [requirement]?"
4. **Automation Focus**: "What tools can automate evidence collection for [control]?"
5. **Audit Perspective**: "What will auditors specifically look for in [area]?"

---

## 🎯 Framework Coverage

- **SOC 2**: Trust Services Criteria (Type I & II)
- **ISO 27001**: 2022 version with 93 controls
- **PCI-DSS**: Version 4.0
- **HIPAA**: Security Rule, Privacy Rule, Breach Notification
- **GDPR**: EU data protection requirements
- **NIST**: CSF 2.0, 800-53
- **CIS Controls**: Version 8

---

## 📚 Related GPTs

- **SecureCodeGPT**: For secure coding controls and code review requirements
- **ThreatModelGPT**: For risk assessment requirements in compliance frameworks
- **PenTestGPT**: For penetration testing evidence (required by many frameworks)

---

## 💡 Questions?

ComplianceGPT works best when you:
- Provide specific framework and scope
- Describe your current environment
- Ask for actionable outputs (not just theory)
- Iterate and refine based on your needs

Start simple and build from there!

