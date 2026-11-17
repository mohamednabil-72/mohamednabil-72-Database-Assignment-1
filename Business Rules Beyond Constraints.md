Some business rules require checking related records or calculating values from multiple transactions. These rules cannot be enforced using only primary keys, foreign keys, NOT NULL, UNIQUE, CHECK, or DEFAULT constraints.
Rule 1 — Blacklisted Customers
SRS Reference: Section 7.7

Business Rule:

A customer who is on the blacklist must not be allowed to create a new reservation.

Why Constraints Are Not Enough:

The system must check whether the customer has an active blacklist record before creating a reservation. This requires checking data in another table.

How to Enforce:

Use application logic to validate the customer's status before saving the reservation. A database trigger or stored procedure can also reject the reservation if the customer is blacklisted.

Rule 2 — Vehicle Transfer Validation
SRS Reference: Section 8 — Stakeholder Interview Notes

Business Rule:

A vehicle must not be transferred to the same branch where it is currently located.

Why Constraints Are Not Enough:

The vehicle's current location depends on its latest transfer record, or its home branch if it has never been transferred. A simple constraint cannot reliably determine the current location from the new transfer record alone.

How to Enforce:

Use a stored procedure to check the vehicle's current branch before inserting a new transfer. The operation must be rejected if the destination branch is the same as the current branch.

Rule 3 — Loyalty Tier Calculation
SRS Reference: Sections 7.10 and 8 — Stakeholder Interview Notes

Business Rule:

A customer's loyalty tier must always match their current points balance:
- Silver: Below 1,000 points.
- Gold: From 1,000 to 4,999 points.
- Platinum: 5,000 points or more.
Why Constraints Are Not Enough:

The points balance is calculated from multiple earned and redeemed transactions. A simple constraint cannot calculate and maintain this total whenever a new points transaction is recorded.

How to Enforce:

Recalculate the customer's points balance and tier whenever a loyalty transaction is recorded, using a stored procedure or application service within the same database transaction. Alternatively, calculate the tier from the transaction history whenever it is requested.