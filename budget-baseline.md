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

