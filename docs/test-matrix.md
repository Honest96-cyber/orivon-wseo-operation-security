# Integration Test Matrix

| Scenario | Expected Tier | Reason |
|---|---|---|
| Infinite ERC20 approval | RED | INFINITE_ALLOWANCE |
| Exact approval amount | GREEN | SAFE_ALLOWANCE |
| Upgradeable proxy with EOA admin | RED | SINGLE_ADMIN_KEY |
| Verified contract with history | GREEN | AUTHENTIC_CODE |
| Fresh deploy with low history | AMBER | LOW_HISTORY |
| Long lockup with no emergency withdraw | RED | NO_EMERGENCY_WITHDRAW |
