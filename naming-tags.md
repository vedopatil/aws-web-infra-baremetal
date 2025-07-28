## AWS Naming Conventions

### Resources
- EC2: `web-prod-us-east-1a-01`
- ALB: `alb-us-east-1-web`
- ASG: `asg-us-east-1-web`
- S3 Buckets: `aws-web-infra-baremetal-us-east-1-logs`

### Tags (Apply to all resources)
- Project = aws-web-infra-baremetal
- Environment = dev / prod
- Owner = vedo
- Confidentiality = public
- Purpose = website / logs / billing / monitor

Why do naming conventions and tags matter in a growing infra?
why? -> Helps group the resources
if not done? -> 1. A total mess of resource tracking and grouping
                2. Many tag dependent functionalities become toothless
                3. Due to tagging failure, a small leak in overal system may result in bankruptcy due to "small" mistake.
