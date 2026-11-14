# Risk Analysis

Risk Score = Probability x Impact. Low 1-5, Medium 6-12, High 13-25.
Ranking: score (high to low), then impact, then Risk ID.

| Rank | Risk ID | Risk | P | I | Score | Priority |
|------|---------|------|---|---|-------|----------|
| 1 | R01 | Double booking of the same seat when requests arrive at the same time | 4 | 5 | 20 | High |
| 2 | R02 | Frequent requirement changes (coupons, cancellation rules, new payment modes) | 4 | 4 | 16 | High |
| 3 | R06 | Project completion delayed beyond the semester deadline | 4 | 4 | 16 | High |
| 4 | R03 | Payment gateway outage or failed callback (money deducted but no ticket issued) | 3 | 5 | 15 | High |
| 5 | R04 | Security vulnerabilities such as SQL injection, weak login or exposed customer data | 3 | 5 | 15 | High |
| 6 | R07 | Slow response at peak booking time (new-release weekend); 3-second target missed | 3 | 4 | 12 | Medium |
| 7 | R08 | Inadequate testing leaves defects in the booking and payment flow | 3 | 4 | 12 | Medium |
| 8 | R10 | Integration failures between the booking, payment and notification services | 3 | 4 | 12 | Medium |
| 9 | R09 | Team member unavailable (exams or illness) | 4 | 3 | 12 | Medium |
| 10 | R05 | Loss of source code or project documents | 2 | 5 | 10 | Medium |
| 11 | R12 | Database failure or data corruption | 2 | 5 | 10 | Medium |
| 12 | R14 | Refund and cancellation rules are left undefined, causing rework | 3 | 3 | 9 | Medium |
| 13 | R13 | Hosting or tool costs exceed the budget | 2 | 3 | 6 | Medium |
| 14 | R11 | E-mail or SMS provider failure, so e-tickets are not delivered | 3 | 2 | 6 | Medium |
| 15 | R15 | Minor UI differences across browsers and phones | 2 | 2 | 4 | Low |

## Top three risks needing immediate attention
1. R01 - Double booking of the same seat when requests arrive at the same time (score 20)
2. R02 - Frequent requirement changes (coupons, cancellation rules, new payment modes) (score 16)
3. R06 - Project completion delayed beyond the semester deadline (score 16)

## Summary
High: 5, Medium: 9, Low: 1, Total: 15
