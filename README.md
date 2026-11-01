# Hi, I'm Faizal Akhtar Bin Azhar

I'm a full-stack software developer and Information Technology graduate from Malaysia, building applications with Java, Spring Boot, React, TypeScript, PostgreSQL and AWS. I'm also preparing for the AWS Certified Developer – Associate exam; I'm not yet certified.

## Featured projects

### Counterline POS

A multi-outlet retail point-of-sale system built with Java 21, Spring Boot, PostgreSQL, React and TypeScript. It is a completed `v1.0.0` portfolio release.

- **Three interfaces from one API:** a tablet POS for cashiers and managers, a customer-facing display, and a back-office dashboard for head office and outlet managers.
- **Multi-outlet:** each outlet has its own staff, till devices and cash registers, with sales reports in the dashboard.
- **Transactional integrity:** idempotent payment recording, optimistic and pessimistic locking, manager-approved voids and refunds, and Flyway-managed PostgreSQL migrations.
- **Testing and CI:** backend integration tests against real PostgreSQL (Testcontainers), Vitest and Testing Library, and Playwright smoke tests. GitHub Actions runs the backend, frontend, CDK and packaged-image checks, including a Trivy scan.
- **AWS deployment verification:** an AWS CDK stack (VPC, ECS Fargate, RDS PostgreSQL, Secrets Manager) was deployed once on 2026-10-31 and checked with a 21-step browser acceptance run ([record](https://github.com/Hollowpath/counterline-pos/blob/main/docs/deployment-verification-2026-10-31.md)).

**The AWS deployment was temporary and has been torn down, so there is no live demo.** To try it, run it locally with Docker as described in the README. All data is synthetic, and payments are recorded rather than processed.

[Source code](https://github.com/Hollowpath/counterline-pos) · [v1.0.0 release](https://github.com/Hollowpath/counterline-pos/releases/tag/v1.0.0)

### ClaimFlow

A serverless employee expense and reimbursement workflow built with TypeScript, React and AWS. Employees submit claims with receipts, managers review them, and finance administrators maintain policy and mark approved claims as paid.

- **Serverless AWS architecture:** CloudFront and S3, API Gateway, Lambda, DynamoDB and S3 receipts, defined with AWS CDK in `ap-southeast-1`.
- **Authentication:** Amazon Cognito sign-in with the authorization code flow and PKCE, plus a JWT authorizer on the API. Roles are checked on the server.
- **Expense workflow:** draft, submit, review, approve or reject, resubmit and pay, with an append-only history of every change.
- **Event-driven processing:** a DynamoDB outbox, EventBridge and SQS with a dead-letter queue clean up receipts and deleted-draft history asynchronously.
- **Testing:** Vitest and React Testing Library, with GitHub Actions checks.

Accounts on the live site are created by an administrator, so it isn't open to self-registration. To try the application without an account, the repository includes local demo instructions that run it on your machine with sample users and no AWS account. ClaimFlow is a portfolio project, not a production system. The repository's collaboration playbook describes how AI-assisted development was used and reviewed.

[Source code](https://github.com/Hollowpath/claimflow) · [v1.0.0 release](https://github.com/Hollowpath/claimflow/releases/tag/v1.0.0) · [Live site](https://d3vq4pyeoivioy.cloudfront.net)

## Open-source recognition

[![XERJ Corpus Hub contributor](https://hub.xerj.org/contributors/Hollowpath/badge.svg)](https://hub.xerj.org/contributors/Hollowpath)

A ClaimFlow DynamoDB implementation was selected for inclusion in the XERJ Corpus Hub, with attribution to this profile and repository.

## Tools I work with

- **Languages:** Java, TypeScript, JavaScript, SQL
- **Backend:** Spring Boot, Spring Security, Spring Data JPA, Flyway, Node.js
- **Frontend:** React, Vite, Tailwind CSS
- **Data:** PostgreSQL, DynamoDB
- **AWS:** Lambda, API Gateway, DynamoDB, Cognito, S3, CloudFront, EventBridge, SQS, ECS Fargate, RDS, Secrets Manager, CDK
- **Testing and delivery:** JUnit, Testcontainers, Vitest, Playwright, Docker, GitHub Actions, Git
