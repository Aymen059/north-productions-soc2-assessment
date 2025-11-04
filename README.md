# 🛡️ SOC 2 Type II Readiness Assessment — North Productions

### 📊 Project Overview
This project simulates a **SOC 2 Type II Security Trust Criteria Readiness Assessment** for **North Productions**, a fictional SaaS company that provides **data-visualization dashboards** to small and midsize businesses.  
The objective was to evaluate five key **Security controls** within the AWS environment, identify **gaps**, and recommend **remediation measures** to align with SOC 2 requirements.

---

### ☁️ Environment Architecture

**AWS Services Deployed**
- **EC2** — Application tier hosting the analytics application  
- **RDS (PostgreSQL)** — Database tier for structured storage  
- **S3** — Storage for log files, exports, and customer datasets  
- **IAM** — Access control and role management  
- **CloudTrail** — Logging and monitoring across all regions  

📎 **Appendix C: [AWS Architecture Diagram (Draw.io)](https://app.diagrams.net/)**

---

### 🔍 SOC 2 Control Mapping & Gap Analysis (5 Controls)

| **SOC 2 Requirement** | **Current State** | **Gap Identified** | **Remediation Recommendation** |
|------------------------|------------------|--------------------|--------------------------------|
| **Access Control / MFA** | Root and IAM users have MFA enabled. No unused access keys. Access Analyzer clean. | None – compliant with SOC 2 access control requirements. | Maintain MFA enforcement and regularly review IAM reports. |
| **Encryption (At Rest & In Transit)** | S3 bucket uses SSE-KMS encryption; HTTPS enforced. | Block all public access = Off. | Enable “Block Public Access” and enforce least privilege for S3. |
| **Logging & Monitoring (CloudTrail)** | CloudTrail enabled for all regions. Verified events (RunInstances, ConsoleLogin) in np-cloudtrail-logs bucket. | No log file validation or alerting for suspicious events. | Enable CloudTrail file validation and integrate alerts with CloudWatch. |
| **Configuration Management** | EC2 NP-App-Server uses key pair auth; ports 22 (admin IP) & 80 (public) configured. | No AWS Inspector or automated patching. | Enable AWS Inspector and schedule patch management. |
| **Backup & Recovery** | RDS encrypted (KMS); backups enabled (1 day); private VPC, not public. | No long-term retention. | Increase backup retention period and test disaster recovery. |

📊 **Appendix A: [SOC 2 Gap Matrix (Google Sheets)](https://docs.google.com/spreadsheets/d/11rA7AnW-QVJV6NnFWMsYKE1izoHkkJRaBJn3qQr3TUw/edit?gid=0#gid=0)**

---

### 🧠 Key Findings
- CloudTrail lacks event validation and automated alerting.  
- S3 bucket allows potential public access misconfigurations.  
- EC2 lacks automated patching and inspection.  
- RDS backup retention period insufficient for SOC 2 audit readiness.  
- MFA properly enforced — fully compliant. ✅

---

### 🛠️ Remediation Actions
1. **Enable CloudTrail file validation** and link with CloudWatch alarms for real-time detection.  
2. **Block all public access** in S3 and review bucket policies.  
3. **Enable AWS Inspector** for vulnerability management.  
4. **Increase RDS backup retention** to 7–14 days.  
5. **Maintain IAM security hygiene** by auditing access reports monthly.  

📘 **Appendix B: [Remediation Document (Google Docs)](https://docs.google.com/document/d/1cWF8hqM0PfCvqfKXUy6i4yYLtB13vaN5sAwffrnii08/edit?tab=t.0)**

---

### 🧰 Tools Used

| **Category** | **Tools / Services** |
|---------------|----------------------|
| Cloud Infrastructure | AWS (EC2, RDS, S3, IAM, CloudTrail, KMS) |
| Compliance Framework | SOC 2 Type II — Security Trust Criteria |
| Documentation | Google Docs, Google Sheets |
| Visualization | Draw.io (Architecture Diagram) |

---

### 🚀 Learning Outcomes
- Built a secure **AWS environment** aligned with SOC 2 principles.  
- Gained hands-on practice with **IAM, CloudTrail, and encryption** controls.  
- Learned to perform **gap analysis** and write professional remediation reports.  
- Strengthened understanding of **compliance readiness** in cloud environments.

---

### 📎 Appendices

- **Appendix A:** [SOC 2 Gap Matrix (Google Sheets)](https://docs.google.com/spreadsheets/d/11rA7AnW-QVJV6NnFWMsYKE1izoHkkJRaBJn3qQr3TUw/edit?gid=0#gid=0)  
- **Appendix B:** [Remediation Document (Google Docs)](https://docs.google.com/document/d/1cWF8hqM0PfCvqfKXUy6i4yYLtB13vaN5sAwffrnii08/edit?tab=t.0)  
- **Appendix C:** [AWS Architecture Diagram (Draw.io)](https://app.diagrams.net/)  
- **Appendix D:** [Main Project Documentation](https://docs.google.com/document/d/1aV9Q5bweXURxLm2gLSGd5M5Qu8816_ajuNVxvDYrvdM/edit?tab=t.0)

---

### 👤 Author
**Aymen Kiyar**  
📍 Northern Virginia  
📧 aymenkiyar950@gmail.com  
🌐 https://www.linkedin.com/in/aymen-kiyar/ 

---

⭐ *If you found this project helpful or insightful, consider starring the repo!*
