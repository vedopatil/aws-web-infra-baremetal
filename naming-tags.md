## AWS Naming Conventions

### Resources
- EC2: `web-prod`
- ALB: `alb-web`
- ASG: `asg-web`
- S3 Buckets: `aws-web-infra-baremetal-logs`

### Tags (Apply to all resources)
- Project = aws-web-infra-baremetal
- Environment = dev / prod
- Owner = vedo
- Confidentiality = public
- Purpose = website / logs / billing / monitor

Why do naming conventions and tags matter in a growing infrastructure?
why? -> Helps group the resources

If not done? -> 1. A total mess of resource tracking and grouping
                2. Many tag-dependent functionalities become toothless
                3. Due to tagging failure, a small leak in the overall system may result in bankruptcy due to a "small" mistake.
