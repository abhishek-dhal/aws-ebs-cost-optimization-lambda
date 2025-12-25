# Cleanup Steps

This document outlines the steps followed to safely remove all AWS resources created during the **EBS Snapshot Cost Optimization using Lambda** project and avoid any unintended charges.

---

## 1. Disable the Scheduler
- Navigate to **Amazon EventBridge → Rules**
- Disable the rule triggering the Lambda function

*Purpose:* Prevents further automated executions.

---

## 2. Delete the Lambda Function
- Go to **AWS Lambda → Functions**
- Select the project Lambda function
- Delete the function

*Purpose:* Stops all snapshot cleanup logic and releases compute resources.

---

## 3. Remove EventBridge Rule
- Delete the EventBridge rule if it was not removed automatically

*Purpose:* Ensures no scheduled triggers remain.

---

## 4. Clean Up IAM Resources
- Detach all policies from the Lambda execution role
- Delete the IAM role created for the project
- Remove any custom IAM policies related to snapshot management

*Purpose:* Prevents unused permissions and follows security best practices.

---

## 5. Delete CloudWatch Log Groups
- Navigate to **CloudWatch → Log groups**
- Delete the log group associated with the Lambda function

*Purpose:* Avoids ongoing log storage costs.

---

## 6. Verify EC2 Snapshots
- Go to **EC2 → Snapshots**
- Filter by **Owner = Self**
- Confirm only intended snapshots were affected

---

## 7. Final Cost Verification
- Review **AWS Billing → Cost Explorer**
- Ensure no active charges related to the project remain

---

## ✅ Conclusion
Completing these steps ensures a clean AWS account state with no residual resources, permissions, or ongoing costs.
