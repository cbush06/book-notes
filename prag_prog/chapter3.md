# Chapter 3 — The Basic Tools

Every craftsman needs a basic set of good quality tools. Tools make your more efficient and more effective. As you master them, your productivity will skyrocket. You should start with a set of generalized tools and gradually add to your tool bag as you encounter new problems and discover new tools to help you solve them. Many practitioners make the mistake of adopting a single *Swiss Army knife*, such as a particular integrated development environment (IDE), office suite, or publishing software, and never leave its cozy interface.

## The Power of Plain Text

> The best form of storing knowledge persistently is *plain text*. With plain text, we give ourselves the ability to manipulate knowledge, both manually and programmatically, using virtually every tool at our disposal. — pg. 73
> 
> **What are benefits of using plain text to store information?**
> 1. Human readability
> 2. Interchangeability — can be easily used in many different kinds of software
> 3. Parsability — easily read from file into software data structures
> 4. Presentation/Formatting — can be formatted, converted, exported, and displayed in limitless ways
> 
> **What are some examples of our use of plain text?**
> 1. Confluence
> 2. Gitbook — MICAPS7 user manual and documentation, these notes
>
> **Can you think of any opportunities for adopting the use of plain text?**

1. **Plain Text** — The authors define it as “printable characters in a form that can be read and understood directly by people.” *However,* we should restrict this definition a little further to text that is actually _plain_ in the sense that it is stored in its rawest form, either ASCII or Unicode. Contrast this with text stored in a particular text editor format (e.g. Word, WordPerfect, Adobe Acrobat, etc.).
2. **Why use Plain Text?** — The authors say it best, "The problem with most binary formats is that the context necessary to understand the data is separate from the data itself." Put another way, in most cases where the information is in a binary format, the originating application is required to present the information in a meaningful form.
3. **TIP 20: KEEP KNOWLEDGE IN PLAIN TEXT**
4. Drawbacks
    1. **Real** (if you're faced with any of these, be sure the benefits are worth the obscurity of a non-plain text format)
        1. May take more space than binary format 
        2. More computationally expensive to process
        3. You prefer major desktop applications to do your editing — before opting for binary, be sure your preferred apps don't support importing/exporting to a plain-text (or markup/markdown) format
    2. **Imagined**
        1. Lack of security — despite the obfuscation offered by binary and other non-plain text formats, they offer no additional protection from file tampering than does plain text
        2. No formatting/styling — using any one of numerous formatting conventions, you can easily style your document and render in it numerous formats (e.g. Gitbook can export your plain text documents to PDF, EPUB, MOBI, and HTML formats as well-styled documents)
5. Other benefits include of plain text include:
    1. Easy to compare 2 versions of the same file
    2. Play nicely with version control systems (Bitbucket, GitHub, SVN, etc.)
    3. No specialized editors required
    4. Anyone can inspect the contents
    5. Can be printed out as-is
    6. Easier for testing
    7. It's self-described and will outlive the alternative
    8. Easy interchange (think Unix-style piping)

## Shell Games

1. The *shell* is a programmer's (and tester's) most powerful tool
    1. Fast and lethally efficient
    2. Allows combining (piping together) commands in powerful ways
    3. Can be enhanced by writing macros to accomplish complex, but common, tasks quickly
    4. Does not limit the user's ability to mentally model and solve problems to the framework imposed by a GUI
2. **TIP 21: USE THE POWER OF COMMAND SHELLS**
3. Often times, GUIs add more complexity than necessary to the use of an application (think SourceTree vs. command line Git). Below are instructions for staging, committing, and pushing all changes in the workspace to a remote git server. Which one is simpler?

| Step | SourceTree                                                                                                                 | Git (shell)                       |
| ---: | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| 1    | From the options menu of the new file, select Stage file. Repeat for all files to be staged.                               | git add .                         |
| 2    | Click the Commit button at the top to commit the file.                                                                     | git commit -am "A commit message" |
| 3    | In the message box, enter a commit message.                                                                                |                                   |
| 4    | Click the Commit button under the box. You can now see your change under the History tab.                                  |                                   |
| 5    | From SourceTree, click the Push button to push your committed changes.                                                     |                                   |
| 6    | Under the Push? column from the dialog box that appears, select the branch where you want to push the change and click OK. | git push                          |

## Power Editing

> **What makes an editor a power editor?**
> 
> **What features should your choice of editor include? Exclude?**

1. Pick one powerful text editor and *master* it!
2. *In the past,* sticking with IDEs led to a modern day *babel* of confusion because you had to use a different IDE for each language/task and every IDE had its own interfaces, shortcuts, command keys, and quirks.
3. Today, I would argue *Visual Studio Code* is a welcome answer to these problems.
4. However, every power user should be proficient with a terminal editor!
5. My recommendations:
    1. For a general purpose IDE, I've found Visual Studio Code to be the best of breed. It offers the flexibility and efficiency of a terminal based editor like Vim with the ease of use of a modern IDE.
    2. For a terminal editor, I recommend *Vim* and here's a handy cheat sheet for it (be sure to CTRL+Click it): [Vim Cheat Sheet](vimcheatsheet.pdf)
6. **TIP 22: USE A SINGLE EDITOR WELL**
7. Times I recommend using a powerful terminal editor:
    1. Fixing merge conflicts
    2. Editing text-based system configuration files
    3. When SSH'ing to a remote machine, it's your only choice
8. Times I recommend using a powerful IDE:
    1. Coding
9. Why do we still use Eclipse?
    1. I still find its integration with Maven to beat out VS Code
    2. The ability to define and export/import coding/formatting standards is huge in a team environment
10. When VS Code can do these 2 things, I leaving Eclipse behind...

## Source Code Control

> **Have you experienced development without source control? What was it like?**
> 
> **Is source control really needed if the project only has a single developer? Why or why not?**
> 
> **How do you go about choosing a source control system? What are the criteria? Why choose one over another?**

1. Source control serves as a GIANT *undo* button
2. Source control can tell you:
    1. Who made changes?
    2. When were they made?
    3. Which version was a change/bug introduced in?
    4. Metrics (lines of code changed, files changed, growth/shrinkage in project size)
    5. Releases of software made
    6. With plugins, you can determine complexity, quality, bug rate, etc.
3. Source control allows:
    1. Branching to isolate new features from main source
    2. Multi-developer collaboration
    3. Fixing bugs in a past release while adding new features to future release
    4. With a CI/CD system, automated building, quality scans, and deployments
4. **TIP 23: ALWAYS USE SOURCE CODE CONTROL**

## Debugging

1. Origins of the word **bug**: Rear Admiral Dr. Grace Hopper (aka - Grandma COBOL) literally found a moth caught in an electromechanical relay in a computer system. She told a technician there was "a bug in the system."
2. Debugging can be an emotional activity because people take pride in their work and often tie their ego to the quality of their product.
3. Instead of denial, finger-pointing, excuses, or other, **treat debugging as PROBLEM SOLVING**
4. Keep in mind that the end goal is to ship a quality product and if someone can help make your work perfect by identifying bugs so you can fix them, *that's a GOOD thing*
5. **TIP 24: FIX THE PROBLEM, NOT THE BLAME**
6. Have the **right mindset**: turn off defenses and disconnect your ego from your code
7. **TIP 25: DON'T PANIC**
8. If you think "that's impossible," you're wrong.
9. When faced with a bug, begin calmly and methodically tracking it own. **Don't just fix symptoms. Find the root cause.**
10. Use good tools:
    1.  Set compiler warnings and debugging output to MAX
    2.  Use a good logging framework. If you don't have one, write out tracing information to the console.
    3.  If working in JavaScript or other browser frameworks, use the browser's debugging console and tools.
    4.  If you just can't figure it out, try explaining the problem to someone else and see if that generates some ideas.
11. **Lastly,** ask for help! Sometimes, a different perspective makes all the difference.
12. **TIP 26: "SELECT" ISN'T BROKEN** — 99% of the time, the problem is not in a library, the operating system, the virtual machine, or anywhere but in your code...**unless you're testing in Internet Explorer...then it's probably Internet Explorer...**
13. When encountering a bug, don't take it at face value. You may see an easy workaround or a *quick fix*, but take the time to determine why the code failed (especially if the code has been around for a while).
14. If a bug resulted from *bad data*, that's no excuse. You need to implement better parameter checking, data cleansing, or exception handling.
15. **TIP 27: DON'T ASSUME IT, PROVE IT**

## Text Manipulation Languages

> Where the authors write *PERL*, you should read *Python*. Python is cleaner, has true OO, easier dependency management, well-suited for data analytics, and is just all-around better (of course, this is only my opinion).
> 
> **What are some opportunities for us to use a scripting/text manipulation language?**

1. Wood workers *work* wood. Steel workers *work* steel. Masons *work* stone, brick, and mortar. **Programmers, analysts, and testers *work* text.**
2. To do this job, we need a general purpose, extensible, fast, and powerful tool: a scripting language
3. Uses:
    1. Transforming a single input into multiple forms of output
    2. Enforcing rules, checks, etc. across a myriad of files
    3. Quickly prototyping an idea...doing a feasibility study
    4. Doing data analysis, calculating some metrics, generating statistics
    5. Generating test/dummy data
    6. Producing documentation
4. **TIP 28: LEARN A TEXT MANIPULATION LANGUAGE**

## Code Generators

> **What is an example of our present-day use of code generators?**
>
> Programmers use Lombok to generate getters, setters, equals, hashcode, constructors, and more.
> Testers might someday use a recorder that generates test cases from their interactions with a browser.

1. In the interest of the *DRY* principle, it is often wise to have a single authoritative source of information or code and automate the generation of its variants (e.g. achieving the same functionality in different contexts).
2. **TIP 29: WRITE CODE THAT WRITES CODE**
3. 2 kinds of code generators:
    1. *Passive* generators run once to produce a result. Any changes to the source code will require the generator to be ran again. An example of such a generator is the JAXB XML schema generator that creates Java entities/classes based on an XML schema.
    2. *Active* generators run each time their results are required (e.g. every time the project is compiled). Lombok is a good example of this kind of generator.
4. Often, code generators are written in a *Text Manipulation Language*