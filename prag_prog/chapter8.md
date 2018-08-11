# Chapter 8 — Pragmatic Projects

## Ubiquitous Automation

> Although computing is still an industry at the Model-T stage, we can’t
> afford to go through two pages of instructions again and again for some
> common operation. Whether it is the build and release procedure, code
> review paperwork, or any other recurring task on the project, it has to
> be automatic. — pg. 230

### All on Automatic

**TIP 61: DON'T USE MANUAL PROCEDURES**

* Where possible, automated procedures should be used in lieu of manual instructions
* Modern tools include:
    * Shell scripts
    * Python, PERL, etc.
    * Virtual machine images
    * Docker
    * Vagrant
    * JUnit
    * Cucumber
    * Cron jobs

### Compiling the Project

* Compiling should/must be automated
* Tools include (plenty of choices):
    * Ant
    * Make
    * Maven
    * Webpack
    * Gradle
    * Gulp
    * Parcel
* Unit tests/regression tests should be _hooked_ into the build process so they are automated

### Build Automation

> **Compiling** is the process of turning source code into object code. **Building** a 
> project includes the other steps required to make a project deployable and executable.
> These include packaging the files, generating installers, running quality checks, and more.

* Builds should be run automatically on a regular schedule
* Many of the tools listed above can automate the process of building the system
* To fully automate _scheduled_ builds, a Continuous Integration/Continuous Deliver system should be used. Such tools include:
    * Jenkins
    * GitLab
    * Concourse
* More advanced tools can even package your application into a virtual machine image so there is zero configuration required to deploy it. Instead, you just drop your VM image into a container orchestration system like Kubernetes and you're done.

### Automation Administrivia

> Because memory is the second thing you lose as you age, we don’t
> want to rely on it too heavily. We can run scripts to perform procedures
> for us automatically, based on the content of source code and
> documents. Our goal is to maintain an automatic, unattended, content-
> driven workflow. — pg. 234

#### Web Site Generation

* Documentation that is extracted from code, requirements analyses, design documents, and any drawings, charts, or graphs all need to be published automatically
* This is the DRY principle in action again
* The various presentations/formats of documents should be generated automatically from their authoritative source

## It's All Writing

**TIP 67: TREAT ENGLISH AS JUST ANOTHER PROGRAMMING LANGUAGE**

* In other words, apply all our _pragmatic principles_ to documentation generated for a project
* 2 kinds of documentation for a project:
    * **Internal** documentation includes source code, comments, and design and test documents
    * **External** documentation is anything shipped or published to the outside world (e.g. user manuals, help files, etc.)
* All documentation is a _mirror of the code._ If there's a discrepancy, the code rules.

**TIP 68: BUILD DOCUMENTATION IN, DON'T BOLT IT ON**

### Comments in Code

* Generating formatted documents from code comments is **easy.** Think JavDoc.
* Donald Knuth took it a step further with his _literate programming,_ but this never really caught on
* In the scientific community, executable reports offer an interesting twist...using code to explain your comments: see [Jupyter Notebook](http://jupyter.org/) and [BeakerX](http://beakerx.com/)

> Except in rare cases (e.g. complex algorithms, mathematical formulas, etc.),
> use comments to explain _why_ not _how_. Your code explains the _how._

* 90% of programming is naming things. Name your variables, methods, and classes **well** and they won't require comments.
* Sometimes, it's even helpful to extract blocks of code into small methods so you can **name the block of code.**

### Executable Documents

* Where possible, store documents as **plain text** with **markup commands**
* Now the document can be processed and exported to a myriad of formats (PDF, epub, modi, HTML, and more)
* Markup formats include:
    * Markdown
    * AsciiDoc
    * Textile
    * reStructuredText
    * LATEX
    * Pendown
* Example tools include:
    * LATEX
    * GitBook
    * HTML (not recommended)
    * Jekyll
    * Hugo
    * VuePress
    * Gatsby
    * Nuxt
    * Sphinx
    * Pendown

### Print It or Weave It

* Hyperlink or import documents into other documents rather than duplicating the information
* This adheres to the DRY principle by maintaining an authoritative source for information
* Many of the tools listed above in "Executable Documents" support this


#### Including one Markdown file in another Markdown file using Gitbook:
```
{% include "./test.md" %}
```