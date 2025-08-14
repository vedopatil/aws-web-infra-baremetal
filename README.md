# aws-web-infra-baremetal

A fully functional, production-simulated, and budget-controlled public website infrastructure.

## Why Document Before Building?

1. **Discipline & Project Tracking:** Ensures a systematic approach and clear progress monitoring.
2. **Transparency:** Building and documenting in a public repository promotes openness and collaboration.
3. **Defined Scope:** Establishes fixed project requirements, making minimum standards a tracked necessity.
4. **Scalability & Onboarding:** Comprehensive documentation is essential for team growth, audits, and onboarding—no one should rely solely on memory.

## Principle of Least Privilege

A zero-trust policy is enforced, granting only the necessary privileges to each stakeholder. This approach prevents unauthorized access and reduces the risk of malpractice in the cloud.

- **Example:** EC2 instances are permitted only to write to S3 logs, not to read all buckets.
- **IAM Roles:** Each role is tightly scoped to its specific task (e.g., monitoring, autoscaling). For instance, an IAM user tasked with adding filtered files to an S3 bucket should not have access to read other files unless explicitly required.

## Environment Separation: Dev vs. Prod

Separating development and production environments is non-negotiable, even in early stages.

- **Development:** Mistakes are less costly and can be safely tested in a controlled environment.
- **Production:** Real business operations occur here; errors can result in significant financial loss or business failure. Only thoroughly tested and verified changes are promoted to production.
- **CI/CD:** Dev environments enable continuous integration and deployment testing, ensuring failures are caught before reaching end users.

## Importance of Cost Guardrails

Deploying infrastructure without cost controls can lead to unmonitored spending and unexpected bills.

- **Risks:** Misconfigured Auto Scaling Groups, overprovisioned EC2 instances, or improper S3 lifecycle management can rapidly inflate costs. AWS does not refund accidental usage.
- **Examples:** Overprovisioned resources can consume budget unnecessarily, and failures to scale down can result in ongoing, avoidable expenses.

---

# Original Content

A fully functional, production-simulated, budget-controlled public website infrastructure.

Why document before building?
1. Discipline and project tracking
2. A public repo, building and documenting in the open, not closed behind the walls
3. A fixed scope of the project is set, and minimum requirements are now a compulsion, a tracked compulsion.
4. Documentation is essential for team scaling, audits, and onboarding future engineers — no one should rely on your memory.


What is the principle of least privilege, and how does it apply here?
A zero-trust policy, where particular and required privileges must be given to all the stakeholders, ensures prevention of unauthorised access and malpractices in the cloud. For our EC2-based website infra, EC2 instances must only have permission to write to S3 logs — not read all buckets. IAM roles must be tightly scoped to each task, like monitoring or autoscaling. For example, if an IAM User has a task of only adding filtered files to the S3 bucket, he should not be given access to read other files in the Bucket, unles specifically required.

Why is separating environments (dev, prod) non-negotiable even in early stages?
A mistake costs very less when done in a controlled, closed environment, dev environment is exactly the same, multiple tests can be carried out, mistakes cost less; prod is where real business goes on, a mistake here, can cost 100K, or even millions, and possibly whole business, so onlyverified things go into prod, this seperation allows maintaining quality, security and durability of the applications. Dev environments also enable CI/CD testing before deployments — any failure gets caught before it hits paying users.

What would happen if you deployed your infrastructure without a cost guardrail in place?
The cost won't be tracked, and there will be no monitoring of spending, which may result in bills crossing the limit you can afford to pay. Also, large-scale infrastructure like misconfigured Auto Scaling Groups, misused provisioned IOPS, or S3 lifecycle mismanagement can silently inflate bills in hours, and AWS will not refund accidental usage. Examples, sometimes, overprovisioned EC2 instances eat cash like a hungry gorilla, and you pay for what you didn't use at all, Auto Scaling Groups when misconfigured, Failures to scale down when required, etc.
