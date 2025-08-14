## IAM Role: `EC2S3_baremetal_role`

This IAM role allows EC2 instances to access the `aws-web-infra-prod-logs` S3 bucket using the `S3ProjectBucketAccessPolicy`.

- **Role Name**: `EC2S3_baremetal_role`
- **Attached Policy**: `S3ProjectBucketAccessPolicy`
- **Trusted Entity**: EC2 service

### Creation Steps (AWS Management Console)

1. Sign in to the [AWS Management Console](https://console.aws.amazon.com/) and go to **IAM**.
2. In the left navigation pane, click **Roles** → **Create role**.
3. **Select trusted entity type**:
   - Choose **AWS service**.
   - Select **EC2**.
   - Click **Next**.
4. **Attach permissions policies**:
   - Search for `S3ProjectBucketAccessPolicy`.
   - Select it and click **Next**.
5. **Role name and review**:
   - Name the role: `EC2S3_baremetal_role`.
   - (Optional) Add a description: *Allows EC2 instances to access production S3 bucket logs.*
6. Click **Create role**.

### Verification

1. In IAM, open `EC2S3_baremetal_role`.
2. Verify the **trusted entity** is EC2.
3. Verify the **attached policy** is `S3ProjectBucketAccessPolicy`.

### Next Step

After creating this role, attach it to your EC2 instance that runs the application to grant it S3 access.
