# aws-web-infra-baremetal
A fully functional, production-simulated, budget-controlled public website infrastructure.

Why document before building?
1. Discipline and project tracking
2. A public repo, building and documenting in the open, not closed behind the walls
3. A fixed scope of the project is set, and minimum requirements are now a compulsion, a tracked compulsion.
4. Documentation is essential for team scaling, audits, and onboarding future engineers — no one should rely on your memory.


What is the principle of least privilege, and how does it apply here?
A zero-trust policy, where particular and required privileges must be given to all the stakeholders, ensures prevention of unauthorised access and malpractices in the cloud.

Why is separating environments (dev, prod) non-negotiable even in early stages?
A mistake costs very less when done in a controlled, closed environment, dev environment is exactly the same, multiple tests can be carried out, mistakes cost less; prod is where real business goes on, a mistake here, can cost 100K, or even millions, and possibly whole business, so onlyverified things go into prod, this seperation allows maintaining quality, security and durability of the applications.

What would happen if you deployed your infrastructure without a cost guardrail in place?
The cost won't be tracked, and there will be no monitoring of spending, which may result in bills crossing the limit you can afford to pay.
