# Layer 4: Real-World Validation

Can developers actually accomplish their goal when they try to build it?

Even when an API is technically correct, understandable at a glance, and documented well enough to choose a path, implementation often reveals issues that weren't visible during review.

Rather than evaluating individual APIs in isolation, this layer evaluates the developer experience that emerges when capabilities are combined to solve real problems and build real products.

## Approach

A robust implementation is created using only publicly available documentation (plus, in the case of an API that hasn't been published yet, the API's final draft) and without predefined guidance on which APIs or capabilities to use.

The implementor is tasked with accomplishing a realistic developer goal and must determine:

* Which capabilities are required.
* How those capabilities fit together.
* How workflows should be executed.
* How implementation challenges should be resolved.

Throughout the implementation process, all points of friction, confusion, failed assumptions, implementation challenges, unexpected behavior, unresolved questions and any solutions found are recorded.

The resulting implementation is evaluated both for successful completion and for the findings generated during the implementation process.

## Observations

Many implementation findings emerge when real-world use cases are tested against actual platform behavior.

Examples include:

* Encountering requirements that weren't apparent until implementation began.
* Discovering that multiple capabilities can't be combined in the expected way.
* Finding that a workflow is significantly more complex than it initially appeared.
* Discovering that a supported capability doesn't actually support the attempted use case.
* Needing information that didn't seem important or relevant until hitting up against it during implementation.

### Example

While validating a set of Stores Catalog v3 APIs, I had AI build a headless store with multiple locations and inventory tracking enabled, working with the v3 products, inventory, locations, brands, ribbons, info sections, customizations, and categories APIs, plus the relevant eCommerce cart, checkout and orders APIs.

Many issues surfaced that review of the individual APIs hadn't predicted. The first pass used Catalog v1 APIs because v3 prerequisites, including requirements during site creation, weren't documented. After switching to v3, variants, inventory locations, and product media each broke in different places. 

Inventory deduction across locations was very confusing. I couldn't get stock to deduct from the correct location. When I reached out to a developer from the team, they explained that Wix Checkout doesn't support multi-location inventory deduction. Inventory would be deducted from the correct location only when an order was created through orders outside of Wix's checkout, assigned with a location ID and marked as paid.

Each API was documented as if it stood alone, but a complex store would use at least 10 APIs, and needed end-to-end flows. A setup workflow was needed with a clear path through variants, locations, inventory and media. Purchasing flows were also needed that spelled out Wix Checkout’s limits for multi-location inventory, and the order path that deducts stock properly for the outlying cases.

Some findings revealed opportunities to improve the APIs. Others exposed limitations that are unlikely to change and needed to be surfaced clearly so developers can make informed implementation decisions. [After the Findings](06-Prioritizing-Developer-Experience-Findings.md) covers how I weighed those against publication pressure when deciding what to push for, drop, or defer.

These are the issues that are most likely to remain invisible until a customer hits a wall.

## Why It Matters

Real-world implementation is where assumptions are tested against reality.

Capabilities that appear straightforward in isolation can behave very differently when combined to support realistic business requirements, and even very experienced reviewers often miss them.

Real-world validation helps identify those risks before developers encounter them themselves.
