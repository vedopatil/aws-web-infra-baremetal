## IAM Policy: `S3ProjectBucketAccessPolicy`

This IAM policy grants permissions to read and write objects in the `aws-web-infra-prod-logs` bucket.

- **Name**: `S3ProjectBucketAccessPolicy`
- **Permissions**:
  - `s3:GetObject` – Retrieve objects from the bucket.
  - `s3:PutObject` – Upload objects to the bucket.
- **Scope**: Only the specified bucket and its objects.

### Policy JSON

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": [
        "arn:aws:s3:::aws-web-infra-prod-logs",
        "arn:aws:s3:::aws-web-infra-prod-logs/*"
      ]
    }
  ]
}
```

### Creation Steps (AWS Management Console)

1. Sign in to the [AWS Management Console](https://console.aws.amazon.com/) and open the **IAM** service.
2. In the left navigation menu, click **Policies**.
3. Click **Create policy**.
4. Select the **JSON** tab.
5. Delete any pre-filled content and **paste** the policy JSON from above.
6. Click **Next**.
7. On the **Review and create** page:
   - Enter **Name**: `S3ProjectBucketAccessPolicy`
   - (Optional) Add a description: *Allows GetObject and PutObject on the aws-web-infra-prod-logs bucket.*
8. Click **Create policy**.
9. Once created, search for `S3ProjectBucketAccessPolicy` in the policies list and click it.
10. On the **Permissions** tab, verify:
    - Actions allowed: `s3:GetObject` and `s3:PutObject`
    - Resource ARNs reference `aws-web-infra-prod-logs` and all objects within it.
