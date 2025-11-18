# CloudSecGPT - Usage Guide

A practical cloud security assistant for AWS, Azure, and GCP. Identifies misconfigurations, reviews IAM policies, and secures infrastructure-as-code.

---

## 🎯 What It Does

- Identifies cloud security misconfigurations
- Reviews IAM/RBAC policies for least privilege
- Analyzes security groups and firewall rules
- Secures Infrastructure-as-Code (Terraform, CloudFormation, etc.)
- Provides remediation with CLI/console/IaC commands
- Maps findings to CIS Benchmarks and compliance frameworks

---

## 📋 How to Use

### 1. Copy Instructions to Your AI Assistant

Copy the contents of `instructions.txt` into:
- **ChatGPT**: Custom GPT instructions
- **Claude**: Project knowledge or system prompt
- **Other AI**: System instructions field

---

## 💬 Example Requests

### Misconfiguration Analysis
```
Review this S3 bucket configuration for security issues:
{
  "PublicAccessBlockConfiguration": {
    "BlockPublicAcls": false,
    "BlockPublicPolicy": false
  }
}
```

```
Is this security group safe?
Inbound: 0.0.0.0/0 on port 22, 443, 3306
```

```
Analyze this Azure Storage account for security risks:
- Public access: Enabled
- Encryption: Microsoft-managed keys
- Firewall: Disabled
```

### IAM Policy Review
```
Review this AWS IAM policy for security issues:
{
  "Effect": "Allow",
  "Action": "s3:*",
  "Resource": "*"
}
```

```
Is this Azure RBAC assignment secure?
User: developer@company.com
Role: Contributor
Scope: Subscription
```

### Infrastructure-as-Code Review
```
Review this Terraform for security issues:

resource "aws_s3_bucket" "data" {
  bucket = "company-data"
  acl    = "public-read"
}
```

```
Analyze this CloudFormation template:

Resources:
  MyDB:
    Type: AWS::RDS::DBInstance
    Properties:
      PubliclyAccessible: true
      StorageEncrypted: false
```

### General Questions
```
What are the top 5 AWS security misconfigurations I should check?
```

```
How do I secure an Azure Storage account?
```

```
Create a secure GCP firewall rule that only allows SSH from my office IP
```

---

## 🎓 Tips for Best Results

1. **Be Specific About Cloud Provider**
   - ✅ "Review this AWS S3 bucket config"
   - ❌ "Review this storage config"

2. **Provide Configuration Details**
   - Paste actual configs (JSON, YAML, HCL)
   - Include resource IDs or names
   - Mention the service (S3, Storage Account, GCS)

3. **Ask for Specific Outputs**
   - "Provide CLI commands to fix this"
   - "Show me secure Terraform code"
   - "Map this to CIS Benchmark"

4. **Context Helps**
   - Mention use case (production, dev, public-facing)
   - Compliance requirements (PCI-DSS, HIPAA)
   - Sensitivity of data

---

## 🔧 Common Workflows

### Auditing Cloud Resources
1. "Check my S3 bucket config for security issues: [paste config]"
2. "Review my security group rules: [paste rules]"
3. "Analyze this IAM policy: [paste policy]"

### Securing IaC
1. "Review this Terraform file for security: [paste code]"
2. "Find security issues in this CloudFormation: [paste template]"
3. "Secure this ARM template: [paste template]"

### Remediation
1. "How do I fix public S3 bucket access?"
2. "Provide CLI commands to restrict this security group"
3. "Rewrite this IAM policy with least privilege"

### Compliance
1. "Map this S3 config to CIS AWS Benchmark"
2. "What CIS controls does this violate?"
3. "Create a compliance checklist for Azure VMs"

---

## 📊 Output Types You'll Get

- **Misconfiguration Analysis**: Issue → Risk → Evidence → Remediation (Console/CLI/IaC)
- **IAM Policy Reviews**: Current policy → Issues → Secure alternative
- **IaC Security Reviews**: Vulnerable code → Secure rewrite → Explanation
- **Security Checklists**: Actionable items per service/resource

---

## ⚠️ Important Notes

- **Not a Scanner**: CloudSecGPT provides guidance; use automated tools (Security Hub, Defender) for continuous monitoring
- **Verify Commands**: Always test in non-production first
- **Context Matters**: Generic advice may not fit your specific use case
- **Keep Updated**: Cloud services change; verify with current documentation
- **Cost Awareness**: Some security features have cost implications

---

## 🚀 Pro Tips

1. **Multi-Cloud Comparisons**: "Compare S3, Azure Blob, and GCS security best practices"
2. **Ask for Detection**: "How do I detect this issue across all my resources?"
3. **Request Automation**: "How can I automate this check in CI/CD?"
4. **Policy-as-Code**: "Create a Sentinel/OPA policy to prevent this"
5. **Compliance Focus**: "What CIS controls does this address?"

---

## 🎯 Platform Coverage

### AWS
- **Compute**: EC2, Lambda, ECS, EKS
- **Storage**: S3, EBS, EFS
- **Database**: RDS, DynamoDB, Aurora
- **Network**: VPC, Security Groups, NACLs
- **IAM**: Policies, Roles, Users
- **Security**: CloudTrail, GuardDuty, Security Hub

### Azure
- **Compute**: VMs, App Service, AKS
- **Storage**: Storage Accounts, Disks
- **Database**: Azure SQL, Cosmos DB
- **Network**: VNet, NSGs, Firewall
- **IAM**: RBAC, Managed Identities
- **Security**: Defender for Cloud, Sentinel

### GCP
- **Compute**: Compute Engine, GKE, Cloud Run
- **Storage**: GCS, Persistent Disks
- **Database**: Cloud SQL, Firestore
- **Network**: VPC, Firewall Rules
- **IAM**: Policies, Service Accounts
- **Security**: Security Command Center

---

## 📚 Related GPTs

- **ComplianceGPT**: For mapping cloud controls to compliance frameworks
- **ThreatModelGPT**: For cloud architecture threat modeling
- **PenTestGPT**: For cloud penetration testing scenarios

---

## 💡 Questions?

CloudSecGPT works best when you:
- Provide specific cloud provider and service
- Paste actual configurations or code
- Ask for actionable outputs (CLI, IaC, console steps)
- Specify compliance requirements if applicable

Start with a specific resource or config and build from there!

