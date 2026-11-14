# Mitigation Plan

## R01 - Double booking of the same seat when requests arrive at the same time
Mitigation: Make the seat hold one atomic database operation (transaction or row lock) and run concurrency tests

## R02 - Frequent requirement changes (coupons, cancellation rules, new payment modes)
Mitigation: Formal change control: every change is logged, estimated and approved before work starts; freeze requirements during a sprint

## R03 - Payment gateway outage or failed callback (money deducted but no ticket issued)
Mitigation: Use an established PCI-compliant gateway with an SLA so payment processing and card-data liability sit with the provider; add retries and a daily reconciliation job

## R04 - Security vulnerabilities such as SQL injection, weak login or exposed customer data
Mitigation: Parameterised queries, password hashing, HTTPS, role-based access, security code review and testing before release; never store card data

## R05 - Loss of source code or project documents
Mitigation: Keep all artifacts in Git with a remote repository on GitHub or GitLab; protect the main branch; commit daily

