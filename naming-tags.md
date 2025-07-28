## AWS Naming Conventions

### Resources
- EC2: `web-prod-us-east-1-01` (e.g., `web-prod-ap-south-1a-01`)
- ALB: `alb-us-east-1-web`
- ASG: `asg-us-east-1-web`
- S3 Buckets: `aws-web-infra-baremetal-us-east-1-logs`

### Tags (Apply to all resources)
- Project = aws-web-infra-baremetal
- Environment = dev / prod
- Owner = vedo
- Confidentiality = public
- Purpose = website / logs / billing / monitor
