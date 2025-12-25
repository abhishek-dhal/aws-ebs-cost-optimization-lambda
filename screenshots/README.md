# 📸 Project Screenshots

This folder contains visual evidence of the successful implementation and execution of the **AWS EBS Snapshot Cost Optimization using Lambda** project.

Each screenshot demonstrates a critical part of the architecture, configuration, and verification process.

---

## 🏗️ Architecture Diagram
**File:** `architecture.png`

- Shows the end-to-end serverless architecture
- EventBridge triggering AWS Lambda
- Lambda interacting with EC2 EBS Snapshots
  

Purpose:
> Helps understand the overall design and data flow at a glance.

---

## 🔐 IAM Role & Policies
**File:** `iam-role.png`

- Displays the Lambda execution role
- Demonstrates least-privilege IAM policy attachment
- Confirms EC2 snapshot permissions (`DescribeSnapshots`, `DeleteSnapshot`)

Purpose:
> Validates security best practices and IAM configuration.

---

## ⚙️ Lambda Configuration
**File:** `lambda-config.png`

- Lambda runtime and handler settings
- Execution role attached to the function
- Region configuration

Purpose:
> Confirms correct Lambda setup and role association.

---

## 📊 Lambda Execution Logs
**File:** `lambda-logs.png`

- CloudWatch Logs showing successful Lambda execution
- Snapshot discovery and deletion logs
- Confirms automation is working as expected

Purpose:
> Proof of successful execution and debugging capability.

---



---

## ✅ Why Screenshots Matter
- Provide **visual proof** of project completion
- Help recruiters quickly verify hands-on AWS experience
- Improve project credibility and professionalism

---

## 📌 Note
Sensitive information such as **AWS Account IDs**, **ARNs**, and **Snapshot IDs** have been masked for security purposes.

---

## 👤 Author
**Abhisek Dhall**  
- GitHub: https://github.com/abhishek-dhal  
- LinkedIn: https://www.linkedin.com/in/abhisekdhall
