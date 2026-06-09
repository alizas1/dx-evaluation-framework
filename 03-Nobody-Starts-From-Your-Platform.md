# Nobody Starts From Your Platform

People adopt platforms because they want to accomplish something.

They may be trying to:

* Launch a business.
* Build an application.
* Extend an existing product.
* Automate a workflow.
* Integrate systems.
* Solve a customer problem.

The platform makes tools available that help them achieve those goals.

In order to succeed, they need to understand which capabilities can help them achieve their goal and how those capabilities fit together.

When they don't have the information they need, developers are left trying to answer questions like:

* Which path should I take?
* Which solution best fits my needs?
* Can the platform support what I'm trying to build?
* What should I do next?

The examples below involve different products, capabilities, and workflows, but they all illustrate the same challenge: empowering developers to move from their goal to a solution.

## Choosing an Implementation Path

Developers building Wix apps typically start with an idea of what they want to create and how they want it to behave. Before they could begin implementation, they needed to choose an app-building framework.

Many would select a framework based on familiarity, perceived simplicity, or their existing skill set (UI Builder vs. CLI), without realizing how significantly that choice would affect their future implementation options.

They would later discover that the extension required to support their intended functionality was'nt available within the framework they chose.

As a result, developers were committing to an implementation path that could never support their intended outcome.

To address this, I created guidance that helped developers to first choose the extension they needed based on the functionality they intended to build, and to then evaluate frameworks based on their support for the relevant extensions.

## Understanding Responsibility

Not every decision involved choosing a framework or capability.
Sometimes developers were simply trying to understand what was happening and what action they should take next.

Developers integrating Email Marketing expected to be able to determine the status of the processes they initiated.

Under certain circumstances, however, an account could enter a warning, suspension, or restriction state that required action from the site owner.

The developer could not resolve the issue themselves.
The status endpoint they expected to use returned a generic error rather than information about the account state or the action required to resolve it.

Developers needed to understand not only the state of the account, but also whether they could take action themselves or whether intervention from the site owner was required. 

I recommended allowing access to account status information even when the account was in a warning, suspension or restriction state so developers could understand what was happening and guide their customers accordingly.

## Choosing a Solution

Large platforms naturally evolve over time.

New capabilities emerge. Existing functionality evolves. Different teams solve related problems in different ways.

As a result, developers are often presented with multiple ways to accomplish similar goals.

One example involved checkout creation.

Developers could discover both Payments Checkout Sessions and eCommerce Checkout Templates.

Both capabilities generate checkout links.

The important distinction was that Checkout Sessions generates one-time links for a specific purchase scenario, while Checkout Templates generates reusable links.

Developers needed enough context to understand which capability aligned with their goals before investing in implementation.

I recommended explicitly explaining when each capability should be used and directing developers to the alternative solution when appropriate.

## Observation

The details vary, but the underlying challenge is remarkably consistent.

Developers needed to decide which framework to use, understand why a workflow had stopped working, or determine which capability best fit their needs.

In each case, success depended on having enough context to make the right decision.

When they have that context, they can move forward confidently.

When they don't, assumptions replace understanding, progress slows, and problems sometimes surface only much later.

Helping developers make informed decisions is one of the highest-leverage opportunities to improve developer experience.
