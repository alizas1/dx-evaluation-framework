# After the Findings

The articles in this portfolio focus on finding developer experience problems. They cover whether developers can construct an accurate understanding of an API, get from their goal to the right capability, find the information they need to implement it, or complete a realistic build from the documentation alone.

I would rank my findings by severity for the API team as a starting point for what would sometimes become a longer conversation about what to fix before publication. The API developer would let me know what was straightforward to fix and what was costly or risky.

That's when I had to decide what to drop, what to push for, and occasionally what to escalate. Each decision came down to the effect on external developers if the issue shipped as-is, weighed against the cost to the API team and whatever feature depended on the API shipping.

## When naming misleads developers

In a Localization API, the developer had added an object called revision which included a version field. However, in Wix revision is a standard field that increments by 1 each time the entity is updated. I flagged the naming as redundant and confusing, and recommended replacing this object name with version info if nesting was necessary.

Because this broke a company-wide standard, and deprecating a field wasn't considered a particularly expensive process, I chose to prioritize this as a significant issue and push back on it even though the developer didn't think it was significant enough to go back and fix.

In a Coupons API review, an operation named Increment Use Count applied a coupon toward a usage limit and incremented an internal use counter. The developer didn't see a problem: from inside the service, that was what the operation did. I pushed for a name that matched what an external developer was trying to do, not what happened to the counter. He disagreed, and resolving it took months. Publication was delayed for unrelated reasons, which gave me the opportunity to keep pushing before it shipped. He eventually agreed to rename it to Redeem Coupon.

Naming findings might look minor in a schema review, but a misleading name that ships anyway leads developers to build on the wrong assumption and discover the mismatch later, usually during implementation.

## When names encode constraints that change

In two reviews, field names hid a Wix-only constraint that wasn't obvious from the name itself. I pushed to make that scope explicit in the field name. Both renames were accepted. But now, as the platform opens those capabilities to third-party apps, these names are becoming a different kind of problem.

In an App Instance API review, the response originally included a field called `whitelist`. The field would return the names of apps installed on the site, but only those approved for publication, which at the time meant only apps made by Wix. I flagged the name as unclear and recommended `installedWixApps`, and the developer accepted the recommendation.

In a Payment Event review, a field identified which app had routed a payment through Wix Payments. I recommended `managingWixAppId` to signal that the managing app was Wix-only. That was accepted too.

Both seemed like the right call at publication. The names matched what the API actually returned, and external developers would no longer have to infer a constraint the old names had hidden. However, I hadn't considered the likelihood that the platform might open those capabilities to third parties. As Wix opens more of its platform for third-party use, these fields are likely to become a problem. Today I would recommend `installedAppIds` and `managingAppIds` with clear documentation describing the limitations.

## When there is no fix before launch

In a Branches API review, developers could create a branch in more than one way. One option was to create a branch from a template, which required passing a template ID. The documentation example showed that path, but I couldn't find where an external developer would obtain a template ID to pass in. I flagged that the doc example assumed a template ID with no path for external devs to get one. The API developer agreed there was no solution yet and made the call to hide the template path from the call until there was.

## When the workflow isn't visible from the API

In an Analytics Sessions API review, the API exposed only get and list operations, and both returned session IDs. For a developer building session replay or recording playback, those IDs on their own aren't enough to get to the recording. They would expect a link, a URL, or a documented path from ID to playback. I flagged it in the review: what is the caller supposed to do with the returned session IDs?

The API developer told me that a third party could display session recordings for those IDs, but didn't elaborate, and I couldn't find the path in the API or documentation. When I asked how they would know which sessions to show, and where the IDs came from, the developer provided more information about the sessions, but not how a third party could access them. It wasn't until I pushed again that the answer shifted. The third party had to capture and store session identifiers on their side when recordings are created, as this API doesn't bridge that gap.

The assumption in [Mental Models](02-Mental-Models.md) is that returned session IDs should be enough to reach a recording. Review surfaced that accessing the playback depends on partner-side setup that wasn't described in the reference.

## Observation

Most findings were straightforward, and the developer fixed them or I agreed to drop them. The harder ones were where the fix was costly, the developer didn't see the issue, or the answer depended on information that wasn't in the API or documentation at all.

That judgment was part of every manual developer experience review. Later it was captured in review guidelines and, eventually, in the effort to scale review described in [Scaling Developer Experience Review](07-Scaling-DX-Review.md).
