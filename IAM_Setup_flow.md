## IAM Admin User Setup Flow

This documents the process for creating a secure IAM administrative user for the project.

### ✅ Purpose

- **User**: `vedant.admin`
- **Purpose**: Web infrastructure admin access
- **Project Tags**:
  - `Purpose: website`
  - `Project: aws-web-infra-baremetal`

---

### 🔐 Step-by-Step IAM User Creation with Administrator Access

1. **Create IAM User Group**
   - Name: `aws-admin-group`
   - Attached Policy: `AdministratorAccess`

2. **Create IAM User**
   - Name: `vedant.admin`
   - Console access: ✅ Enabled
   - Password: Auto-generated or custom set
   - Add to group: `aws-admin-group`
   - Tags:
     - `Purpose = website`
     - `Project = aws-web-infra-baremetal`

3. **Log in as vedant.admin**
   - Use the sign-in link provided by AWS.
   - Use the temporary or custom password.
   - Change the password on first login.

4. **Enable MFA**
   - Navigate to: `IAM` > `Users` > `vedant.admin` > `Security credentials`
   - Click: **"Manage MFA"**
   - Choose: **Virtual MFA device**
   - Scan QR code with authenticator app (e.g., Google Authenticator, Authy)
   - Complete setup by entering two consecutive codes.

5. **Verify MFA is Working**
   - Log out from AWS Console.
   - Log back in as `vedant.admin`.
   - Confirm that MFA challenge is required and successful.

---

### 🔒 Security Notes

- MFA is enabled and verified.
- Admin privileges are managed via group-based permission (`aws-admin-group`).
- No access keys were created (recommended unless programmatic access is required).
- All resources are tagged for traceability and cost tracking.

