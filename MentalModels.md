# Layer 2: Mental Models 
Before developers can build successfully with an API, they need to make sense of it. 
They need to understand what functionality it provides, how it's capabilities fit into the larger platform, and what assumptions they can safely make about its behavior. 
The areas below represent recurring patterns I evaluate when reviewing APIs. 

## Representation & Meaning 

Can developers understand what they're looking at?  

Questions I explore include:  
* Can developers tell what this functionality does?  
* Can they understand how it is intended to be used?  
* Are important concepts clearly defined?  
* Can they distinguish between related concepts?  
* Are related concepts and relationships clearly represented?  
* Can developers interpret the information being returned without additional context?  

### Observations 
Many APIs successfully expose information but provide too little context for developers to understand what that information means or how it should be used. 
Recurring issues include undefined concepts, responses that require domain knowledge to interpret, information whose purpose is unclear, and representations that obscure important relationships. 
Developers are often left asking questions such as:  
* What is this?  
* What does it do?  
* How is it used?  
* What is the difference between these concepts?  
* What should I do with this information?  

### Why It Matters 
Developers build solutions based on their understanding of a system. When that understanding is incomplete, they are forced to fill in the gaps themselves. 
Those assumptions may end up being wrong, creating problems that may not become visible until much later in the development process. 

## Context & Relationships 
Can developers understand how capabilities fit together? 
Questions I explore include:  
* How does this API relate to existing APIs?  
* When should developers use this API instead of another one?
* * How does this capability fit into the larger platform?  
* Does terminology align across related APIs?  
* Are similar concepts represented consistently?  
* Will developers understand how these APIs work together?  

### Observations 
Many APIs make sense when viewed in isolation. The challenge emerges when developers try to understand where those APIs fit within a larger platform. 
I frequently encounter capabilities that overlap with existing functionality, expose similar concepts using different terminology, or solve similar problems in different ways. 
In these situations, the challenge is rarely understanding an individual API. The challenge is understanding the system. 

### Why It Matters 
Developers experience platforms as ecosystems. 
When relationships between capabilities are unclear, developers are forced to construct their own understanding of how the platform works. 
That understanding can easily be incomplete or incorrect. 

## Workflow Understanding

Can developers understand how to accomplish their goals?

Questions I explore include:

* Can developers identify the starting point?
* Can they determine the sequence of actions required?
* Can they understand what happens next?
* Are important lifecycle transitions clear?
* Can they understand how multiple capabilities work together to support a workflow?
* Can they determine how a task is intended to be completed?

### Observations

Many APIs expose the functionality required to accomplish a task while providing little indication of how developers are expected to use that functionality in practice.

Recurring issues include unclear workflow sequencing, hidden prerequisites, incomplete lifecycle understanding, and capabilities that make sense individually but not as part of a larger process.

Developers are often left asking questions such as:

* Where do I start?
* What happens next?
* What is the expected sequence?
* Which endpoint should I use first?
* How does this process actually work?

### Why It Matters

Developers do not build with endpoints in isolation.

They build workflows.

When developers cannot understand how capabilities fit into a larger process, even technically correct APIs become difficult to use successfully.

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
Common examples include assumptions about available data, supported access patterns, relationships between concepts, and behavior that appears obvious but is not explicitly defined. 

### Why It Matters 
An API can behave exactly as designed while still create confusion when developer expectations do not match reality. 
The resulting issues are often difficult to diagnose because developers believe they are using the system correctly.
