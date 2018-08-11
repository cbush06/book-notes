# Chapter 7 — Before the Project

## The Requirements Pit

> The word _gathering_ seems to imply a tribe of happy analysts, foraging for nuggets of wisdom
> that are lying on the ground all around them while the Pastoral Symphony plays gently in the
> background. _Gathering_ implies that the requirements are already there — you need merely to
> find them, place them in your basket, and be merrily on your way. — pg. 202

**It doesn't quite work that way.** Requirements rarely lie on the surface. Normally, they're buried deep beneath layers of assumptions, misconceptions, and politics.

> _I believe requirements are often unacknowledged (or even unknown) habits, patterns, processes,
> and rules documented only in the minds of members of the organization for whom you are building
> a system._

**TIP 51: DON'T GATHER REQUIREMENTS—DIG FOR THEM**

### Digging for Requirements

#### How to Recognize a Requirement While Digging

* Requirements are statements of something that needs to be accomplished. For example: _An employee record may be viewed only by authorized users._
* **Beware** of _business rules disguised as requirements_
    * Consider the difference between: 
        * "Only an employee’s supervisors and the personnel department may view that employee’s records."
        * "An employee record may be viewed only by authorized users."
    * A good analyst would see that for what it is, _a business rule that is subject to change._ 
    * In these cases, the analyst should generalize the business rule into a requirement so developers implement it in a flexible manner that can change with the business rules.
* Often, business rules and policies are implemented as metadata that is used by the system (e.g. storing role-permission mappings in a database table).
* **Beware** of _implementations disguised as requirements_
    * Consider the difference between:
        * "The system must let you choose a loan term."
        * "A list box allows users to select the loan term."
    * Is a _list box_ really the most appropriate control for choosing a loan term? What about a slider? A text box? Radio buttons?
    * Analysts must be careful to leave the implementation details to UX designers and developers, except in those rare cases where the users _demand_ a certain implementation.
* **Beware** of mistaking _how_ users do something for _why_ users do something. 
    * Just because users have always done a task a certain way _does not_ mean it's the best way.
    * **Your development has to solve their _business problem_, not just meet their stated requirements.**
* Become the user! Spend a couple days watching the users do what they do.

**TIP 52: WORK LIKE A USER TO THINK LIKE A USER**

### Documenting Requirements

> Ivar Jacobson proposed the concept of **use cases** in his seminal work _Object Oriented Software Engineering:
> A Use Case Driven Approach_ published in 1992. He has since revised his recommended approach to writing use
> cases in his small, freely available ebook [USE-CASE 2.0](https://www.ivarjacobson.com/publications/white-papers/use-case-ebook).

* When writing use cases, emphasize their _goal-driven_ nature
* Ivar Jacobson's _Use-Case 2.0_ recommends using "Use-Case Slices" that are composed of several related "Use-Cases". This approach is similar in nature to how Agile uses "Epics" composed of "User Stories".
* For more information on writing Use Cases, read Alistair Cockburn's book "Writing Effective Use Cases." The U.S. Government also offers a concise page with advice and Use Case templates at [Use Case](https://www.usability.gov/how-to-and-tools/methods/use-cases.html).
* A big danger in producing a requirements document is being too specific. Good requirements documents remain abstract.

**TIP 53: ABSTRACTIONS LIVE LONGER THAN DETAILS**

### Just One More Wafer-Thin Mint...

> The key to managing growth of requirements is to point out each new
> feature’s impact on the schedule to the project sponsors. — pg. 210

Remember the boiled frogs? _Scope creep_ is very similar in nature. You add _just one more requirement._ And then another...and another... And before you know it, your project's delivery date is so far in the future you wonder if it will ever be completed.

You must track and manage each requirement. The most important part of this process is determining each requirement's impact on the schedule.