## S3 Bucket: `aws-web-infra-prod-logs`

This bucket is provisioned to store production logs for the AWS web infrastructure.  
It has the following configurations:

- **Name**: `aws-web-infra-prod-logs`
- **Versioning**: Enabled (to retain previous versions of objects and prevent accidental deletions)
- **Server-Side Encryption**: Enabled with **SSE-S3** (AES-256 managed by Amazon S3)

### Creation Steps (AWS Management Console)

1. **Navigate to S3**
   - Sign in to the [AWS Management Console](https://console.aws.amazon.com/).
   - Go to the **S3** service.

2. **Create the Bucket**
   - Click **Create bucket**.
   - **Bucket name**: `aws-web-infra-prod-logs`
   - **Region**: Select your desired AWS region.
   - Leave **Block Public Access** settings enabled (recommended).
   - Click **Create bucket**.

3. **Enable Versioning**
   - Open the bucket from the S3 console.
   - Go to the **Properties** tab.
   - Scroll to **Bucket Versioning** and click **Edit**.
   - Select **Enable** and save changes.

4. **Enable Server-Side Encryption (SSE-S3)**
   - Still in the **Properties** tab, scroll to **Default encryption**.
   - Click **Edit**.
   - Select **Enable**.
   - **Encryption type**: **Amazon S3 managed keys (SSE-S3)**.
   - Save changes.

### Verification

- In the **Properties** tab, confirm:
  - **Bucket Versioning** is **Enabled**.
  - **Default encryption** shows **SSE-S3 (AES-256)**.
