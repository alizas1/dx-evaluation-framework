# Scaling Developer Experience Review

"How did you think to ask that?"

It was a question I commonly got from my team, including experienced reviewers, and one I often struggled to answer.

I could regularly identify potential developer experience issues immediately, because the patterns had become instinctive. I recognized them when I saw them, but I couldn't always articulate the reasoning that led me there.

That wasn't a major problem while reviews were performed by humans.
It became a major problem though, when we started exploring AI-assisted review.

If I could identify an issue but couldn't explain the reasoning behind it, I couldn't teach it to an AI system.

At the same time, review demand continued to grow. Every API at Wix was required to pass developer experience review with a technical writer before publication, review capacity remained limited despite additional hiring, and the process had become a frustrating bottleneck for developers.

Before review expertise could be encoded into an AI system, I first needed to understand how we arrived at our conclusions.

## Codifying Review Expertise

I'd attempted to document parts of the review process before, with limited success, but AI-assisted review changed the requirements.

A human reviewer can rely on experience and intuition, but an AI system can't. If I wanted a tool to identify the same issues that experienced reviewers identified, I first needed to explain how those reviewers thought.

I started by iterating on the review guidelines. Every revision attempted to answer questions that experienced reviewers rarely needed to ask themselves explicitly.

- What assumptions should reviewers make about developers?
- How should findings be prioritized?
- What makes an issue severe?
- What information does a developer need in order to succeed?
- What patterns consistently create confusion?

Over time, the guidelines evolved beyond a collection of review criteria and became a way of capturing reviewer judgment.

Codification meant writing down:

* **The evaluation lens** — Developer Experience First: does this genuinely make the API harder for external developers?
* **The audience** — personas, developer intents, and the assumption that a developer may encounter an API in isolation or land on an API that isn't the best fit for their needs.
* **What good looks like** — concrete examples of successful workflows and implementation paths.
* **Prioritization logic** — severity tied to developer impact, implementation risk, and likelihood of confusion.
* **Anti-patterns with reasoning** — common issues, examples, and explanations of how they affect developers.
* **Output expectations** — how findings should be structured, communicated, and prioritized.

The reasoning behind the findings mattered at least as much as the findings themselves. In manual review, those calls played out case by case. [After the Findings](06-Prioritizing-Developer-Experience-Findings.md) describes that process before it was written down here.

Naming reviews weren't really about names. They were about the assumptions developers would make when interpreting an API.

Validity reviews weren't really about consistency. They were about preventing developers from drawing incorrect conclusions about how functionality behaves.

Workflow reviews weren't about documentation completeness. They were about whether developers had enough information to accomplish a goal successfully.

Platform reviews weren't about relationships between APIs. They were about helping developers understand how capabilities fit together and which solution best matched their needs.

AI got infinitely better at both finding the issues and making actionable recommendations when they were connected to a clear developer impact.

## Building an AI Reviewer

The codification effort and the AI review system evolved together. I served as PM, SME, and QA, making all product decisions.

I would run the system against an API, perform a manual review myself, and compare the results. The gaps between the two became the basis for the next iteration.
Each comparison exposed another area where review expertise had not yet been documented clearly enough.

Sometimes the system surfaced valid observations without explaining why they mattered. It tended to prioritize smaller findings while overlooking issues involving developer assumptions, workflow understanding, or platform relationships.

I would update the guidelines, test the changes in the review system, evaluate the output, and repeat the process.
Each round of testing forced me to make more of the review process explicit.

The prompts incorporated many of the same questions reviewers used during manual reviews:

* What assumptions are developers likely to make?
* What information is required to succeed?
* What decisions must developers make?
* What could cause confusion?
* What could prevent successful implementation?

Over time, the AI system became both a review tool and a way of validating the review methodology itself.

If the system couldn't consistently identify an issue that experienced reviewers considered important, it usually meant the reasoning behind that finding had not yet been documented clearly enough.

## Evolving the Review Model

As I worked on improving output quality, I noticed that no matter how much I adjusted the prompts or weighted larger developer experience concerns, the model consistently gravitated toward small, localized issues.
Naming issues, missing descriptions, and similar findings appeared consistently.
Findings involving developer assumptions, platform relationships, workflow failures, or capability selection were far less reliable, despite often having a much greater impact on developer success.
The issues that were easiest for the model to identify weren't necessarily the issues that mattered most.

On most reviews, the AI's output was accurate, and excellent at catching smaller, localized issues, including ones I might miss, like naming problems in deeply nested objects. 
It tended to miss bigger, high-level DX issues, including developer assumptions, workflow understanding, and platform relationships. 

To address this, I redesigned the prompting approach around multiple specialized evaluators.
Rather than asking a single reviewer to identify every type of issue, each evaluator focused on a specific aspect of the developer experience.
The goal was to encourage deeper reasoning within individual evaluation areas while reducing the tendency to over-prioritize smaller, easier-to-detect findings.
The redesign was complete before I left the company, though I didn't have an opportunity to implement and evaluate it in production.

The redesign reflected a broader realization: experienced reviewers don't evaluate APIs from a single perspective. They continuously switch between different modes of analysis, each focused on a different type of developer risk.

## Outcome

The project began as an effort to scale developer experience reviews and relieve a growing review bottleneck.
It became an effort to understand how review expertise works, how experienced reviewers identify developer experience issues, and how that reasoning can be made explicit.

Questions that had previously existed only in the minds of experienced reviewers became documented review practices, evaluation criteria, and eventually the foundation of an AI-assisted review system. That reasoning was the prerequisite. The system was only as good as what we'd written down.

The result was a review process that could be taught, applied more consistently, and partially automated while remaining focused on the same goal that guided manual reviews: helping developers succeed.
