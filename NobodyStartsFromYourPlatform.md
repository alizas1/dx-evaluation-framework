# Nobody Starts From Your Platform

People adopt platforms because they are trying to accomplish something.

They may be trying to:

* Launch a business.
* Build an application.
* Extend an existing product.
* Automate a workflow.
* Integrate systems.
* Solve a customer problem.

The platform makes tools available to help them achieve those goals.

Eventually I realized that some of the biggest developer experience issues emerged while developers were trying to make decisions.

They emerged while developers were trying to answer questions such as:

* Which path should I take?
* Which solution best fits my needs?
* Can the platform support what I'm trying to build?
* What should I do next?

The examples below involve different products, capabilities, and workflows, but they all expose the same challenge: the decisions developers must make on their way from a goal to a solution.

---

## Choosing an Implementation Path

Developers building Wix apps needed to select an app-building framework before they could begin implementation.

Many chose based on familiarity, perceived simplicity, or their existing skill set.

Only later did they discover that the extension required to support their intended functionality was not available within the framework they had chosen.

As a result, developers could commit to an implementation path that could never support their intended outcome.

To address this, I created guidance that helped developers choose the extension they needed based on the functionality they intended to build, and evaluate frameworks based on their support for the relevant extensions.

---

## Understanding Responsibility

Developers integrating Email Marketing expected to be able to determine the status of the processes they initiated.

Under certain circumstances, however, an account could enter a warning, suspension, or restriction state that required action from the site owner.

The developer could not resolve the issue themselves.

The status endpoint they expected to use returned a generic error rather than information about the account state or the action required to resolve it.

Developers needed to understand not only the state of the account, but also whether they could take action themselves or whether intervention from the site owner was required.

I recommended allowing access to account status information even when the account was in a warning, suspension ore restriction state so developers could understand what was happening and guide their customers accordingly.

---

## Choosing a Solution

Large platforms naturally evolve over time.

New capabilities emerge. Existing functionality evolves. Different teams solve related problems in different ways.

As a result, developers are often presented with multiple ways to accomplish similar goals.

One example involved checkout creation.

Developers could discover both Payments Checkout Sessions and eCommerce Checkout Templates.

Both capabilities generated checkout links.

The important distinction was that Checkout Sessions generated one-time checkout links for a specific purchase scenario, while Checkout Templates generated reusable checkout links.

Developers needed enough context to understand which capability aligned with their goals before investing in implementation.

I recommended explicitly explaining when each capability should be used and directing developers to the alternative solution when appropriate.

---

## Observation

Each of these examples involves a different type of decision.

* Which path should I take?

* What is happening?

* Which solution best fits my needs?

The details vary, but the underlying challenge is the same.

Developers need enough context to make informed decisions.

When they have that context, they can move forward confidently.

When they don't, assumptions replace understanding, progress slows, and problems often surface much later.

Helping developers make informed decisions is one of the highest-leverage opportunities to improve developer experience.
