## 💰 AWS Budget Setup Flow: Project Cost Monitoring

This section outlines the setup of a custom AWS budget with alerts for cost tracking before project execution begins.

---

### 🏷️ Budget Overview

- **Budget Name**: `half-dollar-budget`
- **Type**: Custom (not from template)
- **Budget Amount**: `$0.50 USD`
- **Scope**: All AWS services (Recommended setting)
- **Time Period**: Monthly (default)
- **Tags**:
  - `Project = aws-web-infra-baremetal`

---

### 📣 Budget Alert Configuration (SNS Notifications)

To receive budget threshold alerts via SMS, an SNS topic and subscription were created.

---

#### 1. **SNS Topic Creation**

- **Service**: Amazon SNS
- **Topic Type**: Standard
- **Topic Name**: `budget-alerts-topic`
- **Tags**:
  - `Purpose = monitor`
- **ARN**: *(Copied after topic creation)*

---

#### 2. **Create SNS Subscription**

- **Protocol**: SMS
- **Endpoint**: Your personal phone number
- **Linked to Topic**: `budget-alerts-topic`
- **Purpose**: Instant budget alerts via text message

---

#### 3. **Attach Alerts to Budget**

Configured 3 alert thresholds using the SNS topic:

| Threshold (%) | Trigger Level | Action | Notification |
|---------------|----------------|--------|---------------|
| 10%           | $0.05          | None   | ✅ SMS via SNS |
| 50%           | $0.25          | None   | ✅ SMS via SNS |
| 80%           | $0.40          | None   | ✅ SMS via SNS |

> No budget actions (e.g., EC2 stop, service limiters) were set — this is a **monitor-only budget** to track usage proactively before project infrastructure is deployed.

---

### ✅ Final Steps

- **Review Settings**: Confirmed thresholds, scope, and notifications.
- **Create Budget**: Completed setup in AWS Budgets.

---

### 🛡️ Notes & Considerations

- Budget is **proactive**, created before any resources are deployed.
- SNS notifications ensure real-time alerts without needing to check the console.
- No IAM actions or triggers are applied — intended for visibility only.
- Tags allow cost association and filtering per project.

Why should billing alerts be the first thing in any AWS infrastructure?
To avoid losing a ton of money on unused resources, and surprisingly _at scale_, costing an amount, which keeps any mistake away from being called a mistake. 
Eg-1, A startup due to unchecked design, caused 5000 S3 reads, per user visit, where egress costs are the only costs, and the only costs used by CSPs to lock you in their services, so 5000*cost_per_gb*data_extracted_in_gb, became essentially a burn to the pocket, and made a whooping 70K USD bill.
Eg-2, An infinite loop was run by an intern, in an Elastic Beanstalk, the app went to prod, and basically burned a few servers, and incurred a 100K bill; an alert would've stopped this from happening, and an added action would've definitely killed the stopped Beanstalk automatically leving no chance of this mishaps.
