# Design decisions

- **Simple infrastructure on purpose:** focus is operational clarity, not complexity.
- **Group-based IAM:** permissions are applied via groups to scale and remain auditable.
- **Explicit deny for sandbox:** prevents accidental access to risky/billable actions.
- **Manual health checks:** chosen to reduce surprise billing risk while demonstrating ops discipline.
- **Stop instance when not in use:** lifecycle control is part of cost/safety operations.