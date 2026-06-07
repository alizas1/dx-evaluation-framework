## Layer 3: Information Validation

Developers should be able to infer as much as possible from the API itself.

However, some information cannot reasonably be inferred from naming, structure, or behavior alone.

When that occurs, the information required to bridge that gap must be available elsewhere.

Information Validation evaluates whether developers have access to the information required to successfully understand and use a capability.

## Context

Are developers given enough information to understand the capability and determine how it can be used within their own product?

Questions I explore include:

* Are important concepts explained?
* Is relevant business context available?
* Are capabilities and limitations described?
* Is the purpose of the capability clearly communicated?
* Are developers given enough context to understand how this capability fits into their own solution?

### Observations

Many APIs expose functionality successfully but provide insufficient context for developers to determine how that functionality should be applied.

Recurring issues include missing business context, undefined terminology, unexplained limitations, and documentation that describes functionality without explaining its purpose.

Developers often understand what an API does while still struggling to determine how it should be used.

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

These gaps often remain invisible until developers encounter them during implementation.

### Why It Matters

Developers can only make correct decisions using the information available to them.

When critical requirements or limitations are not communicated, developers are forced to discover them through trial and error, often after significant implementation effort has already been invested.
