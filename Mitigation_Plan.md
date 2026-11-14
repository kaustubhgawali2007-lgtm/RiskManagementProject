# Mitigation Plan

Response strategies: Avoidance, Mitigation, Transfer, Acceptance.

## R01 - Double booking of the same seat when requests arrive at the same time
- Response strategy: Mitigation
- Mitigation action: Make the seat hold one atomic database operation (transaction or row lock) and run concurrency tests
- Contingency plan: Run a nightly duplicate-seat check; refund the later booking and offer another seat
- Responsible person: Backend Developer
- Review status: In progress

## R02 - Frequent requirement changes (coupons, cancellation rules, new payment modes)
- Response strategy: Mitigation
- Mitigation action: Formal change control: every change is logged, estimated and approved before work starts; freeze requirements during a sprint
- Contingency plan: Move low-priority changes to the next release and re-plan the sprint with the stakeholder
- Responsible person: Project Manager
- Review status: In progress

## R03 - Payment gateway outage or failed callback (money deducted but no ticket issued)
- Response strategy: Transfer
- Mitigation action: Use an established PCI-compliant gateway with an SLA so payment processing and card-data liability sit with the provider; add retries and a daily reconciliation job
- Contingency plan: Keep the booking as 'payment pending', reconcile with the gateway report, then issue the ticket or refund within 24 hours
- Responsible person: Backend Developer
- Review status: In progress

## R04 - Security vulnerabilities such as SQL injection, weak login or exposed customer data
- Response strategy: Mitigation
- Mitigation action: Parameterised queries, password hashing, HTTPS, role-based access, security code review and testing before release; never store card data
- Contingency plan: Disable the affected feature, patch it, reset affected credentials and inform users
- Responsible person: Security Lead
- Review status: In progress

## R05 - Loss of source code or project documents
- Response strategy: Mitigation
- Mitigation action: Keep all artifacts in Git with a remote repository on GitHub or GitLab; protect the main branch; commit daily
- Contingency plan: Restore from the remote repository or any team member's clone
- Responsible person: Developer
- Review status: Monitoring

## R06 - Project completion delayed beyond the semester deadline
- Response strategy: Mitigation
- Mitigation action: Break work into weekly milestones, track progress on a task board and review it every week
- Contingency plan: Cut optional features (coupons, sales reports) and deliver the core booking flow first
- Responsible person: Team Lead
- Review status: In progress

## R07 - Slow response at peak booking time (new-release weekend); 3-second target missed
- Response strategy: Mitigation
- Mitigation action: Cache show and seat-map data, add database indexes and run load tests before release
- Contingency plan: Scale up the server and show a waiting-queue page during the rush
- Responsible person: DevOps Engineer
- Review status: Planned

## R08 - Inadequate testing leaves defects in the booking and payment flow
- Response strategy: Mitigation
- Mitigation action: Write test cases from the SRS (equivalence, boundary and path testing) and run regression tests on every merge
- Contingency plan: Release a hotfix and extend the test period by dropping low-priority tasks
- Responsible person: QA Lead
- Review status: Planned

## R09 - Team member unavailable (exams or illness)
- Response strategy: Mitigation
- Mitigation action: Cross-train two people on every module and keep documentation current in the repository
- Contingency plan: Reassign the tasks to the backup owner and re-plan the sprint
- Responsible person: Project Manager
- Review status: Planned

## R10 - Integration failures between the booking, payment and notification services
- Response strategy: Mitigation
- Mitigation action: Define interface contracts early, integrate every week and run integration tests with a mock gateway
- Contingency plan: Roll back to the last working version tag and fix the problem on a branch
- Responsible person: Development Team
- Review status: Planned

## R11 - E-mail or SMS provider failure, so e-tickets are not delivered
- Response strategy: Acceptance
- Mitigation action: Accept the risk: the e-ticket is also shown on the booking history page, so no extra development is needed
- Contingency plan: Resend through the other channel or from the admin panel
- Responsible person: Backend Developer
- Review status: Monitoring

## R12 - Database failure or data corruption
- Response strategy: Mitigation
- Mitigation action: Automated daily backups with a tested restore; use transactions for all booking writes
- Contingency plan: Restore the last backup, replay the booking log and show a maintenance page
- Responsible person: Database Administrator
- Review status: Planned

## R13 - Hosting or tool costs exceed the budget
- Response strategy: Avoidance
- Mitigation action: Avoid the cost: use an open-source stack and free-tier hosting, with no paid licences
- Contingency plan: Run the demo on a local or college server
- Responsible person: Project Manager
- Review status: Planned

## R14 - Refund and cancellation rules are left undefined, causing rework
- Response strategy: Avoidance
- Mitigation action: Change the plan: release 1 supports only a full refund before a fixed cut-off; partial refunds are deferred; get written approval
- Contingency plan: Admin approves refunds manually until the rules are final
- Responsible person: Business Analyst
- Review status: Planned

## R15 - Minor UI differences across browsers and phones
- Response strategy: Acceptance
- Mitigation action: Accept the risk: test on the two main browsers only and log cosmetic issues for later
- Contingency plan: Fix in a patch release
- Responsible person: Frontend Developer
- Review status: Monitoring

