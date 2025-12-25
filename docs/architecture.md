# Architecture – AWS EBS Snapshot Cost Optimization

## 📌 Overview
This project follows a **serverless architecture** to automate the cleanup of unused or old **Amazon EBS snapshots** in order to reduce AWS storage costs.

The solution is designed with **simplicity, security, and cost efficiency** in mind.

---

## 🏗️ High-Level Architecture Components

### 1️⃣ Amazon EventBridge
- Acts as the scheduler for the automation
- Triggers the Lambda function at defined intervals (e.g., daily or weekly)

---

### 2️⃣ AWS Lambda
- Executes Python-based logic
- Identifies EBS snapshots owned by the account
- Filters snapshots older than a defined retention period
- Deletes eligible snapshots automatically

---

### 3️⃣ Amazon EC2 (EBS Snapshots)
- Stores EBS volume snapshots
- Snapshots are evaluated based on:
  - Ownership (self)
  - Creation date (age)

---

### 4️⃣ AWS Identity and Access Management (IAM)
- Lambda runs with a **dedicated execution role**
- Permissions follow the **principle of least privilege**
- Only snapshot-related EC2 actions are allowed

---

### 5️⃣ Amazon CloudWatch Logs
- Captures Lambda execution logs
- Used for debugging, auditing, and verification

---

## 🔄 Execution Flow

1. EventBridge triggers the Lambda function
2. Lambda retrieves all **self-owned EBS snapshots**
3. Snapshots older than the retention threshold are identified
4. Eligible snapshots are deleted
5. Execution details are logged in CloudWatch

---

## 🛡️ Security Considerations
- No use of `AdministratorAccess`
- IAM policies scoped only to required EC2 snapshot actions
- Snapshot ownership validation prevents accidental deletion

---

## 🎯 Design Benefits
- Fully serverless (no infrastructure to manage)
- Automated and repeatable
- Cost-efficient and scalable
- Easy to extend with additional rules (tags, notifications)

---

## 📈 Possible Enhancements
- Tag-based snapshot exclusion (e.g., `retain=true`)
- Multi-region snapshot cleanup
- SNS notification before deletion
- Infrastructure as Code using Terraform

---

## 📌 Conclusion
This architecture demonstrates a **real-world AWS cost optimization use case** using serverless services, following best practices for security, automation, and operational efficiency.
