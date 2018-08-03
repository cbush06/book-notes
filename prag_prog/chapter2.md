# Chapter 2 — A Pragmatic Approach

There are certain tips and tricks that apply at all levels of software development, ideas that are almost axiomatic, and processes that are virtually universal. These include: de-duplication, orthogonality, reversibility, tracer bullets, prototypes, wire framing, and domain languages.

## The Evils of Duplication

> **Every piece of knowledge must have a _single_, _unambiguous_, and _authoritative_ representation.**<br/>
> **What are some ways we have created duplication?**<br/>
> Validations of the same data elements are duplicated throughout MICAPS6 and occasionally in MICAPS7.<br/>
> **What are some good design choices we've made to prevent duplication?**<br/>
> The validation framework of MICAPS7 has massively reduced the amount of duplication of data validation in the source code. The *Help/User Manual System* in MICAPS7 is written in Markdown and can be built into a static portion of the application or exported to PDF or Word Documents for the users. Regardless of the final format, the actual information is only written once.<br/>
> **How does duplication make debugging more difficult? Testing? Maintenance?**<br/>
> When code is duplicated, fixing/finding one bug does not mean you have fixed/found all instances of that bug. Inevitably, you keep encountering the same problems over and over and your customers begin to loose faith in your ability to maintain their system(s).<br/>
> **How can we prevent _Inter-developer duplication_? How have we?**<br/>
> Code reviews and technical documentation written for developers by developers are a good start.

1. **TIP 11: DRY — DON'T REPEAT YOURSELF**
2. Most people assume maintenance begins when a application is released, but it is not a *discrete* activity, but a *routine* part of the entire development process.
3. It's easy to duplicate knowledge (specifications, requirements, processes, and software) but in doing so we begin a maintenance nightmare.
4. The *DRY* principle: **Don't Repeat Yourself**
5. Different areas duplication arises
    1. **Imposed duplication.** Developers feel the environment — IDE, API, framework, etc. — forces it.
    2. **Inadvertent duplication.** Developers don't realize they are duplicating.
    3. **Impatient duplication.** Developers get lazy.
    4. **Inter-developer duplication.** Multiple people working a project duplicate information.
6. Imposed Duplication
    1. **Multiple representations of same information.** Use scripts or code generation tools. Import documents/document sections into other documents.
    2. **Documentation in code.** Avoid comments wherever possible. Instead, name variables/functions well. Make your code self-documenting.
    3. **Documentation and code.** Ensure system documentation and source code always agree.
    4. **Language issues.** Hopefully, your compiler will find points of disagreement (e.g. header files disagreeing with implementation files).
7. Inadvertent Duplication
    1. Normalize data models
    2. Always use accessor methods rather than directly accessing data fields — this allows changing the internals of a class/model without breaking the interface to the outside
8. Impatient Duplication
    1. This takes discipline
    2. Code reviews help catch these sorts of mistakes
    3. Planning adequate time for development alleviates some of the pressure
9. Inter-developer Duplication
    1. Have a clear design, strong technical leader, and well-understood division of responsibilities within the design
    2. Have good *documentation for the developers by the developers*
    3. Centralize utility routines, constants, and other re-usable elements
    4. _Read other people's code!_ Whether it's through code reviews or informally
    5. **TIP 12: MAKE IT EASY TO REUSE**
    6. *If it isn't easy, people won't do it.*

## Orthogonality

> **Have you ever experienced non-orthogonal code, documentation, or teams? Provide examples.**<br/>
> **What are some present-day failings of ours in orthogonality? Successes?**<br/>
> MICAPS6 is a massively non-orthogonal system. Many of its components are so inter-connected and inter-dependent with one another that making even the smallest correction can have second and third order affects on other parts of the system.<br/
> PLMS is another good example of a non-orthogonal system. Most of its components are interdependent on one another, even to the point that many rely on other components to initialize or manage their state. Non-orthogonality often appears in the form of components/classes that know too much about each others' inner workings and PLMS is a great example of this symptom.

1. Means independence, decoupling — a change to one thing does not affect another
2. **TIP 13: ELIMINATE EFFECTS BETWEEN UNRELATED THINGS**
3. Components should be self-contained: independent with a single, obvious purpose
4. **Increased Productivity** from Orthogonality
    1. Changes are localized/isolated, thus, reducing development time and complexity
    2. Promotes re-use. Because orthogonal components of code have a clear, well-defined purpose and limited dependencies, they are _easy to plug and play._
5. **Reduced Risk** from Orthogonality
    1. Problematic code is isolated and easy to replace with better code
    2. System is more robust because changes are isolated and do not have unpredictable, rippling effects
    3. Easier to test because you can test individual components in an independent maner
6. Orthogonal Project Teams
    1. When members have *overlapping responsibilities*, there is confusion about who is supposed to do what
    2. With *non-orthogonal teams*, _every change requires a meeting_
7. Orthogonal Design
    1. Systems should be a composition of cooperating, independent modules
    2. Layers are a powerful conceptualization for design orthogonal systems (e.g. OSI model)
8. Toolkits and Libraries
    1. Avoid directly accessing toolkits, APIs, or frameworks; instead, use something like the *[Adapter Pattern](https://en.wikipedia.org/wiki/Adapter_pattern)* or the *[Facade Pattern](https://en.wikipedia.org/wiki/Facade_pattern)*
    2. Use Aspect-Oriented Programming to reduce duplication and isolate changes
    3. Use standard interfaces to access the external implementation (e.g. use JPA's annotations with the Hibernate implementation)
9. Orthogonal Code
    1. **Keep your code decoupled.** Use accessor/mutator methods and make member fields private.
    2. **Avoid global data.**  Explicitly pass context to constructors, functions, etc. Avoid treating singleton's as global data stores.
    3. **Avoid similar functions.** Abstract away similar functionality using tools like the *[Strategy Pattern](https://en.wikipedia.org/wiki/Strategy_pattern)*.
10. Testing
    1. Unit testing orthogonal code is considerably easier. Consider how Spring encourages the use of interfaces and components that have very specific purposes.
    2. Discovered problems/bugs are far more localized, easier to trace to the cause, and less risky to fix.

## Reversibility

1. By following the other tips in this book, reversing decisions at a later time should be relatively painless (e.g. DRY, orthogonality, reusability, etc.)
2. **TIP 14: THERE ARE NO FINAL DECISIONS**
3. Hide third-party software behind interfaces (e.g. Adapter or Facade Pattern)
4. Use metadata to provide configuration input
5. Extract repeated code into Aspects

## Tracer Bullets

> **What would you consider opportune times for using tracer bullets?**<br/>
> When you have a complex problem and need to prove the feasibility of building a solution for it.
> **Have we ever applied this concept before? Was it successful?**<br/>
> MICAPS7 was a tracer bullet in itself. We took the initiative to start building out its basic skeleton to prove the feasiblity of the undertaking before we ever approached the customer to recommend it.<br/>
> **Are there any opportunities to use tracer bullets today?**<br/>
> Yes! A PLMS/LOGWAY merger. Migrating applications off the mainframe. Moving to a container ecosystem for DevOps, application packaging/deployment, and server creation and maintenance. A solution for the SAAR workflow. A single sign-on authentication/authorization system that includes SAAR status in determining user privileges.

1. Requirements for new systems are likely vague and almost certainly slightly off target
2. *Tracer Bullets* help find the shortest path for connecting major components of a system together without fully fleshing out those components — they are a *Proof-of-Concept*
3. **TIP 15: USE TRACER BULLETS TO FIND THE TARGET**
4. Benefits
    1. Users get to see something working early
    2. Developers build a structure to work in (and confidence that it will work)
    3. You have a platform to begin integrating components of the system with
    4. Progress is more easily seen and measured
5. Tracer Bullets ≠ Prototypes
    1. Prototypes demonstrate a specific piece of the system and are generally disposable
    2. Tracer Bullets prove feasibility, provide a demonstration of how things work in practice, and are a skeleton for developers to flesh out.

## Prototypes and Post-it Notes

> **How have we applied prototypes on our projects?**<br/>
> We use wireframes for all proposed solutions for mid-tier change requests.<br/>
> **What are some other opportunities to use code-based or other forms of prototypes?**<br/>
> Building out simple examples of proposed initiatives before pursuing a more labor intensive tracer bullet exercise (e.g. see recommended tracer bullets above).

1. Prototypes are designed to test a specific aspect of the architecture, to analyze and expose risk, and offer chances for correction at an early point during the design phase.
2. Not necessarily code-based. Prototypes can be:
    1. Post-it Notes
    2. Sketches
    3. Wire frames
    4. Whiteboard
3. Things to prototype:
    1. Architecture
    2. New functionality for an existing system
    3. Structure/contents of external data
    4. Third-party APIs, libraries, etc.
    5. Performance issues
    6. User interface design
4. **TIP 16: PROTOTYPE TO LEARN**
5. Details to ignore when prototyping:
    1. Correctness
    2. Completeness
    3. Robustness
    4. Style
6. If coding is required, use high-level scripting languages
7. _When using Prototypes, be sure everyone understands they are disposable_

## Domain Languages

> **What are some examples of our present-day use of domain languages?**<br/>
> The validation framework for MICAPS7 is akin to a domain language. Thought it is Java code, it is worded and designed in such a way that it reads like a domain language.<br/>
> **What are some opportunities for their application?**<br/>
> Abstracting the validation framework out of Java code and into a true domain language. We might even store these *configurations* in the database so they are not compiled into the application and can be changed on-the-fly.

1. *Domain Languages *are mini-languages tailored to a specific application domain (using the vocabulary of that domain)
2. Doesn't need to be executable — might just be a way to document user requirements
3. Can easily be turned into an interpreted scripting language — providing a much easier avenue for converting user requirements into executable software
4. **TIP 17: PROGRAM CLOSE TO THE PROBLEM DOMAIN**
5. Mini-languages can easily be implemented using simple string parsing tools. More complicated ones can be built using libraries like *Lex* and *Yacc* to generate parsers.
6. Data languages/Imperative languages can be used for providing configuration files, recording simple macros, or being expanded into executable code by parsers.
7. Embedded languages can be used to allow scripted configuration of a larger system (e.g. Lua, Python, Tcl)

## Estimating

> **How did we go about building a model for estimating MICAPS7? Breaking the model down into its components? Formulating the final estimate?**<br/>
> We first listed all screens that would have to built. Then we added components of the system that didn't have any screens to the list. The we categorized these by complexity and estimated man-days for each task.<br/>
> **So far, how accurate have we been with estimating? What could we do differently next time?**<br/>
> Prior to losing a team member, our estimates were reasonably accurate. In the future, we might consider generating several estimates for varying levels of staffing.

1. **TIP 18: ESTIMATE TO AVOID SURPRISES**
2. Units make a difference! More Precise Scale → More Accurate Estimate.

|Duration	|Quote Estimate in	|
|---	|---	|
|1-15 days	|days	|
|3-8 weeks	|weeks	|
|8-30 weeks	|months	|
|30+ weeks	|avoid giving an estimate	|
|	|	|

1. If possible, ask someone who's already done it
2. Build a mental model of the problem (i.e. think through the steps, resources, complexities, etc. required)
3. Try to break the model down into its constituent components and estimate each of those individually
4. Continue to revise the schedule with each iteration of development
5. **TIP 19: ITERATE THE SCHEDULE WITH THE CODE**
6. Always, always, always say “I'll get back to you” when asked for an estimate
