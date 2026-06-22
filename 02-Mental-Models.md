# Layer 2: Mental Models

Before developers can build successfully with an API, they need to make sense of it.
They need to understand what functionality it provides, how its capabilities fit into the larger platform, and what assumptions they can safely make about its behavior.

Can developers make sense of what they see in the API and its documentation, given only what is there?

The areas below represent recurring patterns I evaluate when reviewing APIs.

## Representation & Meaning

Can developers understand what they're looking at?

Questions I explore include:
* Can developers tell what this functionality does?
* Can they understand how it is intended to be used?
* Are important concepts clearly defined?
* Can they understand the difference between related concepts?
* Can they interpret the information being returned without additional context?

### Observations

Many APIs successfully expose information but don't provide enough context for developers to understand what that information means or how it should be used.
Recurring issues include undefined concepts, responses that require domain knowledge to interpret, information whose purpose is unclear, and representations that obscure important relationships.

Developers are often left asking questions such as:
* What is this?
* What does it do?
* How is it used?
* What is the difference between these concepts?
* What should I do with this information?

### Example

In a Bookings Availability API, four near-synonyms appeared across endpoints and fields: availability, time slots, available, and bookable. None were defined in the platform terminology list. Developers reading the reference would have to infer whether these described the same concept, different stages of scheduling, or different resource states. I recommended defining each term, collapsing overlap where possible, and aligning names with a single vocabulary before publication.

### Why It Matters

Developers build solutions based on their understanding of a system. When that understanding is incomplete, they make assumptions.
Those assumptions may end up being wrong, creating problems that may not become visible until much later in the development process.

## Context & Relationships

Can developers understand how this capability relates to others in the platform?

Questions I explore include:
* How does this API relate to other APIs in the platform?
* Does terminology align across related APIs?
* Are similar concepts represented consistently?
* Will developers understand how these APIs work together?

### Observations

An API might make sense when viewed in isolation but become confusing when developers try to understand where it fits within a larger platform.
I frequently encounter capabilities that overlap with existing functionality, expose similar concepts using different terminology, or solve similar problems in different ways.
In these situations, developers need to understand how the platform is organized and where each capability fits within it.

### Example

In a Contacts API, subscription status lived on `primaryEmail` and `primaryPhone`, while full contact data lived under `info.emails` and `info.phones`. The field names suggested parallel structures, but the objects differed in shape and purpose. This mismatch was potentially confusing: it was hard to tell which location held subscription state versus full contact records. I recommended either aligning the object shapes or documenting explicitly that primary fields carry subscription metadata, not duplicates of `info`.

### Why It Matters

Developers experience platforms as ecosystems.
When relationships between capabilities are unclear, developers are forced to construct their own understanding of how the platform works.
That understanding can easily be incomplete or incorrect.

## Workflow Understanding

Can developers understand how to accomplish their goals using this capability?

Questions I explore include:

* Can developers identify where they should start?
* Can they see a clear path from one endpoint to the next?
* Can they understand what happens next?
* Are important lifecycle transitions clear?
* Can they understand how multiple capabilities work together to support a workflow?
* Is the workflow they need to complete obvious to them?

### Observations

Many APIs expose the functionality required to accomplish a task while providing little indication of how developers are expected to use that functionality in practice. The workflow exists, but developers are left to reconstruct it themselves.

Recurring issues include unclear workflow sequencing, incomplete lifecycle understanding, and capabilities that make sense individually but not as part of a larger process.

Developers are often left asking questions such as:

* Where do I start?
* What happens next?
* What is the expected sequence?
* Which endpoint (or API) should I use first?
* How does this process actually work?

### Example

In an Invoices API, create, update, publish, and payment operations were each documented in the reference, but nothing explained how an invoice moved from draft to published to paid, or which calls were valid at each state. Developers could invoke individual operations correctly and still assemble an invalid sequence. I recommended documenting at least one complete lifecycle flow, including which status transitions each operation supports.

### Why It Matters

Developers don't build with endpoints in isolation. They build workflows.

When developers can't understand how capabilities fit into a larger process, even technically correct APIs become difficult to use successfully.

## Assumptions & Expectations

What assumptions are developers likely to make?

Questions I explore include:
* What behavior will developers expect?
* What information will they expect to be available?
* What access patterns will they expect?
* What relationships will they assume exist?
* What conclusions are they likely to draw from the information available to them?

### Observations

Developers rarely approach an API without expectations. Those expectations are shaped by previous experience, industry conventions, and familiarity with similar capabilities.
Many review findings emerge from identifying assumptions that seem reasonable from a developer's perspective but are not actually supported by the API.
Common examples include assumptions about available data, supported access patterns, relationships between concepts, and behavior that appears obvious but isn't explicitly defined — and that doesn't always exist.

### Example

In an Analytics Sessions API, `Get Sessions` returned a list of session IDs. For a developer building session replay or recording playback, those IDs on their own aren't enough to get to the recording. They would expect a link or URL. I recommended either returning recording links (or another actionable resource) in the response, or documenting clearly how IDs map to their end goal.

### Why It Matters

An API can behave exactly as designed and still create confusion when developer expectations don't match reality.
The resulting issues are often difficult to diagnose because developers believe they are using the system correctly.
