## 🔐 Security Group Setup: Baseline Web Access for EC2

This documents the creation of a minimal, secure baseline Security Group for EC2.

---

### 📌 Scope

- **Service**: Amazon EC2
- **Purpose**: Securely expose a web server to HTTP traffic only
- **Tags**:
  - `Project = aws-web-infra-baremetal`
  - `Purpose = website`

---

### 🔧 Security Group Configuration

- **Name**: `http-web-access-sg`
- **Description**: Allows inbound HTTP traffic only (no outbound traffic)
- **VPC**: Default or custom (per project architecture)

---

### 🔓 Inbound Rules

| Type  | Protocol | Port Range | Source       | Description     |
|-------|----------|------------|--------------|-----------------|
| HTTP  | TCP      | 80         | 0.0.0.0/0    | Public HTTP     |

---

### 🔒 Outbound Rules

| Type  | Protocol | Port Range | Destination | Description |
|-------|----------|------------|-------------|-------------|
| None  | —        | —          | —           | All outbound traffic **blocked** |

> Default outbound rule was **deleted** to enforce strict egress control.

---

### ✅ Final Notes

- Security group is **inbound-restricted to HTTP only**, with **zero outbound** traffic allowed.
- Designed as a **baseline hardened group** to minimize exposure and force explicit outbound configuration if required.
- Ideal for **zero-trust or proxy-controlled architectures**.

