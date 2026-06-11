# After the Findings

The articles in this portfolio focus on finding developer experience problems: whether developers can construct an accurate understanding of an API, get from their goal to the right capability, find the information they need to implement it, or complete a realistic build from the documentation alone.

I would rank my findings by severity for the API team as a starting point for what would sometimes become a longer conversation about what to fix before publication. The API developer would let me know what was straightforward to fix and what was costly or risky.

That's when I had to decide what to drop, what to push for, and occasionally what to escalate. Each decision came down to the effect on external developers if the issue shipped as-is.

In a Localization API, the developer had added an object called `revision` which included a `version` field. However, in Wix `revision` is a standard field that increments by 1 each time the entity is updated. I flagged the naming as redundant and confusing, and recommended replacing this object name with `versionInfo` if nesting was necessary.

Because this broke a company-wide standard, and deprecating a field wasn't considered a particularly expensive process, I chose to prioritize this as a significant issue and push back on it even though the developer didn't think it was significant enough to go back and fix.

Naming findings might look minor in a schema review, but if the name ships wrong, developers build on the wrong assumption and discover the mismatch later, usually during implementation.

## When there is no fix before launch

In a Branches API review, developers could create a branch in more than one way. One option was to create a branch from a template, which required passing a template ID. The documentation example showed that path, but I couldn't find where an external developer would obtain a template ID to pass in. I flagged that the doc example assumed a template ID with no path for external devs to get one. The API developer agreed there was no solution yet and made the call to hide the template path from the call until there was.

## When the workflow isn't visible from the API

In an Analytics Sessions API review, the API exposed only get and list operations, and both returned session IDs. For a developer building session replay or recording playback, those IDs on their own aren't enough to get to the recording. They would expect a link, a URL, or a documented path from ID to playback. I flagged that in the review: what is the caller supposed to do with the returned session IDs?

The API developer told me that a third party could display session recordings for those IDs, but didn't elaborate, and I couldn't find the path in the API or documentation. When I asked how they would know which sessions to show, and where the IDs came from, he provided more information about the sessions, but not how a third party could access them. When I pushed again, the answer shifted to something the API doesn't provide: the partner has to capture and store session identifiers on their side when recordings are created.

The assumption in [Mental Models](02-Mental-Models.md) is that returned session IDs should be enough to reach a recording. Review showed what the API and documentation alone wouldn't: reaching playback depends on partner-side setup that isn't described in the reference.

## Observation

Most findings were straightforward: the developer fixed them or I agreed to drop them. The harder ones were where the fix was costly, the developer didn't see the issue, or the answer depended on information that wasn't in the API or documentation at all.

That judgment was part of every manual developer experience review. Later it was captured in review guidelines and, eventually, in the effort to scale review described in [Scaling Developer Experience Review](07-Scaling-DX-Review.md).
