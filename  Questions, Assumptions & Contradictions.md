1. Questions
1. Luxury vehicle pricing --- Section 7.3
   Some luxury vehicles have their own prices instead of following the
   category rate. Should these prices be stored as a separate
   vehicle-level price history, and should they use the same
   validity-period rules as category rates?
2. Customer blacklist --- Section 7.7
   Can a customer be removed from the blacklist after the issue has
   been resolved? If so, should the system keep the removal date and
   the employee who approved it?
3. Corporate monthly invoices --- Section 7.16
   The SRS says corporate clients are usually invoiced monthly rather
   than paying for each rental. What information should an invoice
   contain, and how should payments be allocated when one invoice
   covers several rentals?
4. Additional rental drivers --- Section 7.12
   What details must be recorded for an additional driver, and can the
   same driver be added to more than one rental?
5. Supplier records --- Section 7.15
   Should suppliers have an official supplier code, or is the supplier
   name sufficient to identify them?
2. Assumptions
1. Supplier identifier --- Section 7.15
   A SupplierID is used as the primary key because the SRS lists
   supplier name, phone number and email, but does not provide a unique
   supplier identifier.
2. Loyalty transaction identifier --- Section 7.10
   A separate LoyaltyTransactionID is used to identify each points
   movement because the SRS requires every movement to be recorded but
   does not specify a transaction number.
3. Contract discount identifier --- Section 7.8
   A separate DiscountID is used to identify each corporate category
   discount because no discount identifier is specified in the SRS.
4. Category rate history --- Section 7.3
   Each category rate is stored with a validity start date and end date
   so that the rate applicable during a past period can be identified.
   The SRS requires historical rates to be retained but does not
   prescribe the exact date fields.
5. Blacklist history --- Section 7.7
   A blacklist entry is stored as a separate record containing the
   reason, date and responsible branch manager. The SRS does not
   clarify whether a customer may have more than one blacklist record
   over time or how a blacklist is removed.
6. Corporate monthly billing --- Section 7.16
   Monthly corporate invoices are noted as a business requirement, but
   a complete invoice structure and its relationship to rentals and
   payments are not defined in the SRS. They are therefore left for
   clarification rather than being fully specified in the current
   design.
3. Contradictions
- No explicit contradictions were identified in the SRS.
  Some requirements need clarification, particularly luxury vehicle
  pricing and corporate monthly billing, but the document does not
  state two directly conflicting rules.