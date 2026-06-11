# Developer Experience Portfolio

By Aliza Solomon

How can we tell if developers will succeed? Are we doing our best to set them up for success?

The work in this portfolio grew out of these questions.

The articles explore recurring patterns I encountered while reviewing APIs, developing review methodologies, validating implementations, and building systems designed to scale developer experience evaluation.

Together, they examine how developer experience issues come about, and how we can identify and address them before they reach developers.

## Contents

### 1. [Evaluating API Developer Experience](01-Evaluating-API-Dev-Experience.md)

A layered approach to API evaluation: understanding, navigation, information, and implementation — each revealing risks the others miss.

### 2. [Mental Models](02-Mental-Models.md)

Can developers construct an accurate understanding of what they're looking at — and what breaks when they can't?

### 3. [Nobody Starts From Your Platform](03-Nobody-Starts-From-Your-Platform.md)

The decision point between understanding a capability and having the information to use it: can developers get from their goal to the right solution?

### 4. [Information Validation](04-Information-Validation.md)

How information that appears complete can still fail to answer the questions developers need answered.

### 5. [Real-World Validation](05-Validation.md)

What you learn by building realistic implementations from public documentation alone — and logging friction as you go.

### 6. [After the Findings](06-Prioritizing-Developer-Experience-Findings.md)

What happened after review listed the issues: which findings were worth pushing on, and what shipped before publication.

### 7. [Scaling Developer Experience Review](07-Scaling-DX-Review.md)

An effort to scale API review that became an effort to understand how experienced reviewers think — and document that reasoning.

## Where This Work Comes From

When I joined Wix, there was no formal developer experience review process. Most issues surfaced during documentation review of the JavaScript SDK (Velo), after the REST and RPC underneath had already been designed. When APIs were hard to understand or implement, teams worked around it in the SDK wrapper layer. By the time they wanted to publish REST, that workaround debt had accumulated into a long list of breaking changes that were too late to implement.

I established developer experience review during API design, which became a required step of API publication. Over that time I reviewed roughly 300 APIs across Stores, Bookings, Payments, Contacts, Analytics, and most other platform domains. The articles below are the evaluation model that emerged from this work.

- Established developer experience review at Wix; a required publication gate
- Reviewed ~300 APIs across most platform domains
- Trained reviewers and codified review judgment ([Scaling Developer Experience Review](07-Scaling-DX-Review.md))
- PM, SME, and QA for an AI-assisted DX review tool

## Finding Problems Before Developers Do

In my experience, most developer experience issues can be found before developers encounter them, if you know where to look.

The examples in this portfolio are drawn from years of API review, platform guidance, reviewer training, implementation validation, and AI-assisted evaluation work. The same issues appeared repeatedly, though often at different points in the process. Some became visible while developers were deciding which solution to use. Others emerged when information was missing, assumptions were incorrect, or implementation exposed constraints that were not apparent during review.
