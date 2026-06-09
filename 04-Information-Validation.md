# Layer 3: Information Validation

Can developers find the factual information they need to execute the solution they chose?

As much as possible, developers should be able to infer the information they need from the API itself.

However, some information can't reasonably be inferred from naming, structure, or behavior alone.

In these cases, the information required to bridge that gap must be available elsewhere.

## Context

Are developers given enough information to understand the capability and determine how it can be used within their own product?

Questions I explore include:

* Is relevant business context available?
* Are capabilities and limitations described?
* Is the purpose of the capability clearly communicated?
* Are developers given enough context to understand how this capability fits into their own solution?

### Observations

Many APIs expose functionality successfully but don't provide sufficient context for developers to determine how to apply that functionality.

Recurring issues include missing business context, unexplained limitations, and documentation that describes functionality without explaining its purpose.

Developers often understand what an API does while still struggling to determine how it should be used.

### Example

In a Payment API, the documentation centered on receipts without clarifying whether other document types were supported or planned, including invoices. Developers evaluating the API for a broader billing integration could not tell from the reference whether it would meet their needs. I recommended documenting supported document types and planned scope.

### Why It Matters

Understanding functionality is only part of successful integration.

Developers also need enough context to determine whether a capability is appropriate for their use case and how it should be incorporated into their product.

## Dependencies & Constraints

Are important requirements, limitations, and non-obvious behaviors documented?

Questions I explore include:

* Are prerequisites documented?
* Are dependencies explained?
* Is conditional behavior documented?
* Are important limitations described?
* Are workflow requirements clearly communicated?
* Are developers informed about information they could not reasonably infer on their own?

### Observations

Many developer-facing issues emerge not from missing functionality, but from missing information about how that functionality behaves.

Recurring issues include undocumented prerequisites, conditional requirements, hidden dependencies, unsupported scenarios, and workflow requirements that are not communicated clearly.

Some of these gaps remain invisible during review and surface only during implementation.

### Example

In a Contacts API, Update Contact was described as a partial update, but the example did not match that description, and the docs never explained what happens to fields developers leave out. A developer sending only the fields they intended to change could still clear emails, phones, or labels in production. I recommended documenting which fields update, which merge, and what omission means for nested contact data.

### Why It Matters

Developers can only make correct decisions using the information available to them.

When critical requirements or limitations are not communicated, developers are forced to discover them through trial and error, often after significant implementation effort has already been invested.
