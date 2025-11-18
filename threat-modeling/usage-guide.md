# ThreatModelGPT - Usage Guide

## What It Does

Helps security professionals and developers create comprehensive threat models to identify, analyze, and mitigate security threats in systems, applications, and infrastructure.

---

## Setup

### ChatGPT
1. Go to https://chat.openai.com
2. Click your profile → "My GPTs" → "Create a GPT"
3. Click "Configure"
4. Fill in:
   - **Name**: `ThreatModelGPT`
   - **Description**: `Expert threat modeling assistant for identifying and mitigating security threats using STRIDE, PASTA, and other frameworks.`
   - **Instructions**: Copy everything from [instructions.txt](./instructions.txt)
5. Click "Save"

### Claude
1. Create a new Project
2. Copy everything from [instructions.txt](./instructions.txt)
3. Paste into "Project knowledge"

---

## How to Use

### Start a New Threat Model
```
I need to create a threat model for [describe your system/application]
```

### Analyze Specific Components
```
Analyze threats for this authentication flow: [describe flow]
```

### Apply Specific Methodology
```
Use STRIDE to analyze this API gateway architecture
```

### Quick Assessment
```
What are the top 5 threats for a [type of system]?
```

---

## Supported Methodologies

### STRIDE (Primary Framework)
- **Spoofing** - Identity threats
- **Tampering** - Data integrity
- **Repudiation** - Audit/logging
- **Information Disclosure** - Confidentiality
- **Denial of Service** - Availability
- **Elevation of Privilege** - Authorization

### Additional Frameworks
- **PASTA** - Process-driven threat analysis
- **DREAD** - Risk scoring (Damage, Reproducibility, Exploitability, Affected users, Discoverability)
- **LINDDUN** - Privacy threat modeling
- **Attack Trees** - Visual threat decomposition
- **Kill Chain** - Attack progression analysis

---

## Use Cases

### Web Application Threat Model
```
Create a threat model for a web application with:
- React frontend
- Node.js API backend
- PostgreSQL database
- User authentication with JWT
- Payment processing integration
```

### Cloud Infrastructure
```
Threat model for AWS infrastructure:
- EC2 instances in private subnets
- RDS database
- S3 for file storage
- API Gateway + Lambda
- Multi-account setup
```

### Microservices Architecture
```
Analyze threats for a microservices platform with:
- 10+ microservices
- Service mesh (Istio)
- Kubernetes orchestration
- gRPC and REST APIs
```

### Mobile Application
```
Threat model for iOS/Android app that:
- Stores sensitive data locally
- Communicates with backend API
- Uses OAuth2 authentication
- Processes payment information
```

---

## Output Components

Every threat model includes:

### System Overview
- System description and criticality
- Data classification
- Key assets

### Architecture
- Component breakdown
- Trust boundaries
- Data flows

### Threat Analysis
For each threat:
- STRIDE category
- Attack scenario
- Likelihood & Impact
- Risk score
- Existing controls
- Recommended mitigations
- Priority level
- MITRE ATT&CK mapping

### Mitigation Roadmap
- Immediate actions (P0)
- Short-term (P1)
- Long-term (P2)

---

## Example Session

**User:** Create a threat model for a user authentication system using JWT tokens

**ThreatModelGPT Response:**

```
## SYSTEM OVERVIEW
- Name: JWT Authentication System
- Description: REST API authentication using JWT tokens
- Criticality: High
- Data Classification: Confidential

## ARCHITECTURE

Components:
1. Frontend Application - User interface
2. Authentication API - Login endpoint
3. Token Service - JWT generation/validation
4. User Database - Credential storage

Trust Boundaries:
- Between frontend and API (Internet)
- Between API and database (Internal network)

Data Flows:
1. User → Auth API: Credentials (username/password)
2. Auth API → Database: Credential verification query
3. Auth API → User: JWT token
4. User → Application API: JWT in Authorization header

## THREAT ANALYSIS

### Threat 1: JWT Secret Key Exposure
**STRIDE Category**: Information Disclosure
**Affected Component**: Token Service
**Attack Scenario**: If the JWT secret key is exposed (hardcoded, leaked in logs, or stored insecurely), attackers can forge valid tokens and impersonate any user.
**Attacker Profile**: External attacker with access to source code or logs
**Likelihood**: Medium
**Impact**: Critical
**Risk Score**: High
**Existing Controls**: None specified
**Recommended Mitigations**:
1. Store JWT secret in secure vault (AWS Secrets Manager, HashiCorp Vault)
2. Rotate secrets regularly (every 90 days)
3. Use asymmetric keys (RS256) instead of symmetric (HS256)
4. Implement key management lifecycle
**Priority**: P0
**MITRE ATT&CK**: T1552.001 (Credentials in Files)

[... additional threats ...]
```

---

## Common Commands

**Start threat modeling:**
```
Create a threat model for [system type]
```

**Focus on specific threats:**
```
What are the authentication threats in this system?
```

**Apply framework:**
```
Use DREAD scoring to prioritize these threats
```

**Get mitigations:**
```
What are the recommended mitigations for [specific threat]?
```

**Update existing model:**
```
We added a new API gateway. Update the threat model.
```

---

## Best Practices

✅ **Do:**
- Provide detailed system architecture
- Include data flows and trust boundaries
- Specify asset criticality
- Update threat models when system changes
- Focus on high-value assets first
- Consider multiple attacker profiles

❌ **Don't:**
- Skip system understanding phase
- Ignore business context
- Create threat models once and forget
- Focus only on technical threats
- Provide vague system descriptions

---

## Specializations

**Application Security:**
- OWASP Top 10 threats
- API security
- Authentication/Authorization
- Input validation

**Cloud Security:**
- IAM threats
- Data storage security
- Network segmentation
- Container security

**Infrastructure:**
- Network threats
- Physical security
- Supply chain risks
- Insider threats

**Privacy (LINDDUN):**
- Data collection threats
- PII exposure
- Tracking risks
- Compliance (GDPR, CCPA)

---

## Integration with Development

**In Design Phase:**
```
We're designing a new feature: [describe]. What threats should we consider?
```

**Code Review:**
```
Review this authentication code for security threats: [paste code]
```

**Architecture Review:**
```
Evaluate this architecture diagram for security threats
```

**Risk Assessment:**
```
Prioritize these threats for our sprint planning
```

---

## Output Formats

Threat models can be generated in formats for:
- Security documentation
- Risk registers
- Sprint planning
- Compliance audits
- Security architecture reviews

---

## Limitations

- Requires detailed system information
- Cannot access actual system configurations
- Recommendations are guidelines, not guarantees
- Should complement (not replace) security testing
- Threat landscape evolves - models need updates

---

## Questions?

Create an issue in the repo or reach out to the maintainers.

