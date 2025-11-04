
# 🛡️ SOC 2 Type II Readiness Assessment — North Productions

### 📊 Project Overview
This project simulates a **SOC 2 Type II Security Trust Criteria Readiness Assessment** for **North Productions**, a fictional SaaS company that provides **data-visualization dashboards** to small and midsize businesses.  
The goal was to identify **security control gaps** in the company’s AWS infrastructure and provide **remediation recommendations** aligned with SOC 2 principles.

---

### ☁️ Environment Architecture

**AWS Services Deployed**
- **EC2** — Application tier hosting the web analytics app  
- **RDS (PostgreSQL)** — Structured database tier  
- **S3** — Secure storage for reports and customer datasets  
- **IAM** — Access control and role-based permissions  
- **CloudTrail** — Logging and monitoring across all regions  

![AWS Diagram](assets/aws-architecture-diagram.png)

---

### 🔍 Control Mapping & Gap Analysis

Ten key SOC 2 controls were evaluated under the **Security** category:

| **SOC 2 Requirement** | **Current State** | **Gap Identified** | **Remediation Recommendation** |
|------------------------|------------------|--------------------|--------------------------------|
| Access control & MFA | IAM users without enforced MFA | MFA not required for console logins | Enforce MFA via IAM policy |
| Encryption (in transit & at rest) | S3 bucket encryption off | Data unencrypted at rest | Enable default KMS encryption |
| Logging & Monitoring | CloudTrail configured in single region | Missing multi-region coverage | Enable all-region trail |
| Change Management | No version control for infra changes | Lack of change documentation | Use AWS Config & Git versioning |
| Incident Response | No IR policy or contact flow | Undefined escalation procedures | Create IR runbook and escalation contacts |
| Vendor Risk Management | No vendor risk evaluation | Third-party risks untracked | Develop vendor assessment checklist |
| Security Awareness Training | No training tracking | Employees untrained on AWS security | Launch annual awareness training |
| Backup & Recovery | RDS automated backups enabled | No DR testing | Implement backup validation tests |
| Configuration Management | No config baselines | Manual setup | Use IaC tools (CloudFormation) |
| Vulnerability Management | No routine scans | Missing patch management plan | Schedule monthly Nessus scans |

📄 **Full Matrix:** [`deliverables/SOC2_Gap_Matrix.xlsx`](deliverables/SOC2_Gap_Matrix.xlsx)

---

### 🧠 Key Findings
- Encryption at rest not enforced in S3 → potential data exposure risk  
- MFA not applied to all IAM users → identity compromise vulnerability  
- CloudTrail not configured for all regions → incomplete visibility  
- Absence of a formal incident response plan  

---

### 🛠️ Remediation Actions
1. **Enabled KMS encryption** on all S3 buckets  
2. **Configured CloudTrail** for multi-region logging  
3. **Created IAM policies** enforcing MFA and least privilege  
4. **Documented** Incident Response Plan & Change Management process  

---

### 📁 Evidence Artifacts

| **Control** | **Screenshot / Artifact** |
|--------------|---------------------------|
| Encryption | ![S3 Encryption Proof](assets/s3-encryption-proof.png) |
| CloudTrail Logging | ![CloudTrail Evidence](assets/evidence-cloudtrail.png) |
| IAM Policy | Included in SOC2_Gap_Analysis_Report.pdf |
| Backup Verification | RDS snapshot logs attached |

---

### 🧰 Tools Used

| **Category** | **Tools / Services** |
|---------------|----------------------|
| Cloud Infrastructure | AWS (EC2, S3, RDS, IAM, CloudTrail, KMS) |
| Compliance Framework | SOC 2 Type II (Security) |
| Documentation | Google Docs, Excel, PDF Export |
| Visualization | Draw.io / Lucidchart for architecture diagram |

---

### 🚀 Learning Outcomes
- Developed understanding of **SOC 2 control frameworks**  
- Gained hands-on experience with **AWS security best practices**  
- Practiced **gap identification and remediation planning**  
- Built professional deliverables for a **compliance readiness assessment**

---

### 📦 Deliverables
- **SOC 2 Gap Matrix:** [`SOC2_Gap_Matrix.xlsx`](deliverables/SOC2_Gap_Matrix.xlsx)  
- **Gap Analysis Report:** [`SOC2_Gap_Analysis_Report.pdf`](deliverables/SOC2_Gap_Analysis_Report.pdf)

---

### 🧩 Folder Structure
