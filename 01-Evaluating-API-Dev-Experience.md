# Evaluating API Developer Experience

Developer experience isn't defined by whether an API works.
It's defined by whether developers can successfully achieve their goals with it.

- An API can be technically correct and still fail developers.
- Developers can understand what an API is and still lack information required to use it effectively.
- Information can be available and implementation can still expose challenges that were not visible during review.

Over years reviewing public APIs, writing and evaluating documentation, building test implementations, and designing evaluation systems, I repeatedly encountered the same pattern:

Teams focused on whether an API was correct, while developers cared whether they could successfully use it.

Those are not the same thing.

This framework emerged from an effort to answer a simple question:

> How can we determine whether developers will succeed?

## The Framework

Understanding whether developers will succeed requires evaluating more than the API itself. Different evaluation techniques expose different categories of developer experience risk.

Developer experience risk shows up in layers:

1. **Structural correctness**: Is the API technically correct?
2. **Mental models**: Can developers construct an accurate understanding?
3. **Information validation**: Is the information required for success available?
4. **Real-world implementation**: Can developers successfully accomplish their goals?

Each layer reveals different risks. Success at one layer doesn't guarantee success at another; evaluating only one creates false confidence.

### Beyond structural correctness

Structural correctness is a necessary gate: schema validity, auth patterns, error handling, consistency. When it fails, developers can't succeed. This portfolio focuses on the risks that remain even when that gate passes, where APIs are technically sound but developers still struggle.

The articles that follow examine these risks in practice:

- [Mental Models](02-Mental-Models.md)
- [Nobody Starts From Your Platform](03-Nobody-Starts-From-Your-Platform.md)
- [Information Validation](04-Information-Validation.md)
- [Real-World Validation](05-Validation.md)

## Where This Comes From

This framework emerged from years of evaluating APIs from the perspective of developer success.

When I joined Wix, there was no formal developer experience review process. Most developer experience issues surfaced during documentation review, after the API had already been designed and implemented.

I focused on identifying developer experience issues earlier in the design process, when recommendations could still influence the API itself. The platformization team then made developer experience review a required stage of the API publication process, bringing developer experience considerations into API design.

During that time, I reviewed hundreds of APIs across a wide range of platform domains, validated documentation, trained reviewers, developed review guidelines, built test implementations, and later helped design an AI-assisted review system.

During most of this period, DX review focused on mental models and information validation. We tried to implement real-world validation, but building realistic implementations took much longer than the publication process allowed. All that changed when we got access to AI tools. Validation became practical, and it revealed issues review alone hadn't surfaced.

Across all of this work, the same categories of developer experience issues appeared repeatedly across different products, teams, and implementation scenarios.

Some issues were visible during API review. Others appeared only when validating documentation. Others emerged only when attempting to build a realistic implementation.

The framework is an attempt to organize those observations into a model that explains where different types of developer experience risks appear and how they can be identified.

## Applying the Framework

Each article focuses on a different category of developer experience risk, from platform understanding and capability selection to information validation and implementation challenges.

Taken together, they show that developer success depends on a chain of decisions, assumptions, information, and implementation details, and that failures can emerge at any point along that path.
