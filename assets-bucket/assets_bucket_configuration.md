# S3 Bucket Configuration: `aws-web-infra-prod-assets`

This document describes the configuration steps and best practices for the production assets S3 bucket used in the AWS web infrastructure.

## Bucket Name
- `aws-web-infra-prod-assets`

## Configuration Steps

1. **Enable Versioning**
   - Versioning is enabled to retain previous versions of objects and prevent accidental deletions or overwrites.

2. **Enable Logging**
   - Access logging is enabled for this bucket.
   - **Log Destination Bucket:** `aws-web-infra-prod-logs`
   - Note: Logging to a separate bucket (`aws-web-infra-prod-logs`) is essential to avoid recursive logging loops, which can occur if a bucket logs to itself.

## Best Practices
- **Separation of Concerns:** Logging to a dedicated logs bucket ensures clean separation and easier log management.
- **Security:** Ensure that only necessary permissions are granted to users and services interacting with the assets bucket.
- **Monitoring:** Regularly review logs in the `aws-web-infra-prod-logs` bucket for access patterns and potential security issues.

---

_This configuration supports robust asset management and auditability for production workloads._
