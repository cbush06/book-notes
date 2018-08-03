# Chapter 1 — A Pragmatic Philosophy

_Pragmatic Programmers_ look beyond the immediate problem they are solving and ask “How does my code fit into the larger context? What impact does it have on the project as a whole?”

## The Cat Ate my Source Code

1. Responsibility is something you actively agree to (i.e. you have the right _not_ to take responsibility for an impossible situation!)
2. **TIP 3: PROVIDE OPTIONS, NOT EXCUSES**
    1. When plans fall through and you're not able to fulfill your obligation, make arrangements/contingencies/alternatives not excuses
    2. Don't say “it can't be done,” figure out what *can* be done

## Software Entropy

> **What causes “software rot” around our office?**<br/>
> Hunt tells us, “There are many factors that can contribute to software rot. The most important one seems to be the psychology, or culture, at work on a project.

1. **Software Rot:** when *disorder* increases in a software system
2. Despite the best plans, people, technology, tools, etc., a project can still experience decay

> **What are some broken windows in our projects and how can we board them up or fix them?**<br/>
> Duplicated validation rules in MICAPS, inconsistent user experiences (different error messages for the same error, different labels for buttons that do the same thing), code that's not unit tested, processes that should be automated but aren't, ignored browser errors and compiler warnings, outdated APIs, etc.

3. **TIP 4: DON'T LIVE WITH BROKEN WINDOWS** 
    1. Fix each one as soon as it is discovered
    2. If you don't have time to fix it properly, *board it up* and record it to be fixed later at a set time — set a deadline and a reminder so it's not forgotten
4. Boarding up broken windows: 
    1. Document it and assign responsibility for it (e.g. a JIRA ticket)
    2. Log a message (e.g. Log4j TRACE message)
    3. Notify the end user/tester (e.g. return an HTTP “503 Service Unavailable” message, display a pop-up, etc.)

## Stone Soup and Boiled Frogs

> **What are some examples of times we have made “stone soup”? What are some “stone soup” projects we should undertake?**<br/>
> MICAPS7 was a “stone soup” project. We realized it was quickly becoming more costly, error-prone, and time-consuming to maintain it than it would be to rebuild it using modern architecture and technology. A PLMS/LOGWAY merger is a “stone soup”-worthy project because PLMS is an antiquated, desktop application with code that is riddled with broken windows. The responsibilities of PLMS and LOGWAY overlap and complement each other in such a way that a single application could nicely replace them both and benefit the end users in many ways.

1. Sometimes _you have to be the catalyst_
2. There are times when you must be prepared to “beg for forgiveness” rather than “asking for permission” — especially when your end goal is in everyone's best interest
3. _Start-up Fatigue_: people guarding their resources, wanting to form committees, required budget approvals
4. _Prototypes_ and _Wireframes_ are good tools for Hunt's (pg. 8) solution, “Work out what you can reasonably ask for. Develop it well. Once you've got it, show people, and let them marvel.”
5. People find it easier to join an ongoing success. — Hunt, pg. 8
6. **TIP 5: BE THE CATALYST FOR CHANGE**
    1. Be the person who builds the prototype or wireframe
    2. Be the person who writes “the way forward” presentation or the proposal paper

> **What are the consequences of putting off fixing or boarding up broken windows? Who is the “boiled frog”?**<br/>
> The “boiled frog” Hunt mentions is a metaphor for developers who grow too comfortable with the broken windows in their project; in fact, they grow so comfortable that the project reaches a point where it cannot be salvaged. Hopefully, if that time comes, someone steps up and makes *stone soup*.

## Good-enough Software

> **What are some tools/techniques we can use to make ourselves and the customers comfortable with the thought of deploying imperfect software?**<br/>
> Provide meaningful error messages when things go wrong. Provide the end-users with access to logging output so they can include it in error reports or provide it to a help desk agent. Record all logging output to the database or a rolling log file. Integrate a bug reporting form into the application.

1. Software should be “good enough”: it needn't be perfect
2. **TIP 7: MAKE QUALITY A REQUIREMENTS ISSUE**
    1. Reach an agreement on *acceptable* quality for each release
    2. Document these expectations
    3. Ensure they agree the document is accurate
    4. Hold yourself to the document — only exceed the expectations if you have time and resources and if nothing else takes a back seat
3. Code, and the system it's a part of, *will never be perfect*. _Know when to stop._

## Your Knowledge Portfolio

> **What are some resources for building our knowledge portfolios?**<br/>
> What you're doing now! Read forums and tech news (e.g. slashdot, hacker news). Join IEEE and read their Computer, IEEE Spectrum, or Software magazines.

1. As the value of your knowledge declines, so does your value to your company or client. — Hunt, pg. 12
2. **TIP 8: INVEST REGULARLY IN YOUR KNOWLEDGE PORTFOLIO**
    1. _Invest regularly_: read — always; stay informed of new trends, technologies, techniques, tools
    2. _Diversify_: try out different languages and frameworks; test new tools; study other areas of application development (we mainly deal with reporting/logistics apps, try out a big data project, build a game, etc.)
    3. _Manage risk_: practice safe bets (business/enterprise apps) and a few risky ones (games, IOT, uncommon languages)
    4. _Buy low, sell high_: pick an emerging technology that looks promising (AI, Go, Rust) and play with it
    5. _Review and rebalance_: evaluate your skillset as if you were hunting a new job...how marketable are you?
3. **TIP 9: CRITICALLY ANALYZE WHAT YOU READ AND HEAR** — just because a language, IDE, API, or process is new/shiny/popular doesn't mean it's sound or effective. Think!

## Communicate

> **How can we communicate better in our code?**<br/>
> Read the book “Clean Code: A Handbook of Agile Craftsmanship” by Robert C. Martin

1. Nearly everything we do involves communicating (e-mails, meetings, messaging, naming variables and functions, commenting code, etc.) — we'd better do it well:
    1. Know what needs to be communicated: 
        1. What does this function do? 
        2. What does this variable store? 
        3. What's the main idea of this e-mail?
    2. Know your audience: 
        1. If a developer 5 years from now comes along and I'm not here to explain this code, can he/she figure out what's going on and maintain it? 
        2. Is this e-mail going to be read by a technical or non-technical person?
        3.  What do I hope to accomplish by communicating with this person?
    3. Choose your moment: when's the best time for the audience to get the message?
    4. Choose a style: pithy; concise; downright poetic; collegiate with flowing prose and 7 syllable words
    5. Make it look good: sometimes presentation is every bit, if not more, important that content
    6. Get back to people: don't forget to respond to e-mails; keep interested parties in the loop
2. **TIP 10: IT'S BOTH WHAT YOU SAY AND THE WAY YOU SAY IT **— sometimes, presentation is every bit, if not more, important than content
    1. **W**hat do you want them to learn?
    2. What is their **i**nterest in what you’ve got to say?
    3. How **s**ophisticated are they?
    4. How much **d**etail do they want?
    5. Whom do you want to **o**wn the information?
    6. How can you **m**otivate them to listen to you?