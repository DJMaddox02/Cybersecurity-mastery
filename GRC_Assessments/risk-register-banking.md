# Risk Register - Banking Institution (GRC Assessment)
- Date Completed: 10/01/2024
- Source: Google Cybersecurity Certificate - Risk Management Exercise
- Folder: GRC_Assessments

## Operational Environment
- Location: Coastal area with **low crime rate**
- Employees: 100 on-premise, 20 remote
- Customer Base: 2,000 individual accounts, 200 commercial accounts
- Partnerships: Sponsored by a professional sports team and 10 local businesses
- Regulatory Requirements: Subject to **strict finacial regulations**, including Federal Reserve daily cash minimums

# Risk Register Table
| Asset                | Risk                      | Description                                     | Likelihood | Severity | Priority (LxS) |
|----------------------|---------------------------|-------------------------------------------------|------------|----------|----------------|
| Funds                | Buisness Email Compromise | Employee tricked into revealing sensitive info  | 2          | 2        | 4              |
| User Database        | Compromised               | Weak encryption on customer data                | 2          | 3        | 6              |
| Finacial Records     | Leak                      | Backup database exposed pubicly                 | 3          | 3        | 9              |
| Physical Cash        | Theft                     | Safe left unlocked                              | 1          | 3        | 3              |
| Supply Chain         | Disruption                | Delays from natural disasters                   | 1          | 2        | 2              |

## Notes
- **Third-party risk** increases due to buisness partnerships with external vendors.
- **Theft** is possible but less likely due to low-crime enviornment.
- **Financial Records leak** is the highest priority score (score of 9), due to exposure of sensitive backups.

## Risk Response Recommendations
- Implement stronger email authentication training ( phishing simulations)
- Encrypt all customer data with industry-standard methods
- Review backup access controls
- Rotate physical safe access codes regularly
