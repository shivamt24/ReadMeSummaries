This is a summary of the book "The Pragmatic Programmer" written by Andrew Hunt and David Thomas.  
Note: This summary is provided as a reference and should not be considered a substitute for the book. I strongly encourage readers to purchase and read the book to develop a thorough understanding of the concepts presented here.

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->
# Table of Contents
- [Table of Contents](#table-of-contents)
- [Chapter 1. A Pragmatic Philosophy](#chapter-1-a-pragmatic-philosophy)
  - [1. The Cat Ate My Source Code](#1-the-cat-ate-my-source-code)
  - [2. Software Entropy](#2-software-entropy)
  - [3. Stone Soup and Boiled Frogs](#3-stone-soup-and-boiled-frogs)
  - [4. Good enough soup](#4-good-enough-soup)
  - [5. Your Knowledge Portfolio](#5-your-knowledge-portfolio)
    - [Building Your Portfolio](#building-your-portfolio)
    - [Goals](#goals)
  - [6. Communicate](#6-communicate)
- [Chapter 2. A Pragmatic Approach](#chapter-2-a-pragmatic-approach)
  - [7. The Evils of duplication](#7-the-evils-of-duplication)
  - [8. Orthogonality](#8-orthogonality)
  - [9. Reversibility](#9-reversibility)
  - [10 Tracer Bullets](#10-tracer-bullets)
    - [Tracer Bullets Don't Always Hit Their Target](#tracer-bullets-dont-always-hit-their-target)
    - [Tracer Code versus Prototyping](#tracer-code-versus-prototyping)
  - [11. Prototypes and Post-it Notes](#11-prototypes-and-post-it-notes)
    - [Things to Prototype](#things-to-prototype)
    - [How to Use Prototypes](#how-to-use-prototypes)
    - [Prototyping Architecture](#prototyping-architecture)
    - [How Not to Use Prototypes](#how-not-to-use-prototypes)
  - [14. Domain Languages](#14-domain-languages)
  - [15. Estimating](#15-estimating)
    - [How Accurate Is Accurate Enough?](#how-accurate-is-accurate-enough)
    - [Where Do Estimates Come From?](#where-do-estimates-come-from)
    - [Estimating Project Schedules](#estimating-project-schedules)
    - [What To Say When Asked For An Estimate](#what-to-say-when-asked-for-an-estimate)
    - [Challenges](#challenges)
- [Chapter 3. The Basic Tools](#chapter-3-the-basic-tools)
  - [16. The Power of Plain Text](#16-the-power-of-plain-text)
  - [17. Shell Games](#17-shell-games)
    - [A Shell of your own](#a-shell-of-your-own)
  - [18. Power Editing](#18-power-editing)
    - [What Does “Fluent” Mean?](#what-does-fluent-mean)
    - [MOVING TOWARD FLUENCY](#moving-toward-fluency)
    - [Growing your editor](#growing-your-editor)
  - [19. Version Control](#19-version-control)
    - [Version Control As A Project Hub](#version-control-as-a-project-hub)
  - [20. Debugging](#20-debugging)
    - [Psychology Of Debugging](#psychology-of-debugging)
    - [A Debugging Mindset](#a-debugging-mindset)
    - [Where To Start](#where-to-start)
    - [Debugging Strategies](#debugging-strategies)
      - [**Reproducing Bugs**](#reproducing-bugs)
      - [**Code In A Strange Island**](#code-in-a-strange-island)
      - [**Bad Results**](#bad-results)
      - [**Sensitive To Input Values**](#sensitive-to-input-values)
      - [**The Binary Chop**](#the-binary-chop)
      - [**Logging and/or Tracing**](#logging-andor-tracing)
      - [**Rubber Ducking**](#rubber-ducking)
      - [**Process Of Elimination**](#process-of-elimination)
      - [**The Element Of Surprise**](#the-element-of-surprise)
      - [**DEBUGGING CHECKLIST**](#debugging-checklist)
  - [21. Text Manipulation](#21-text-manipulation)
  - [22. Engineering Daybooks](#22-engineering-daybooks)
- [Chapter 4. Pragmatic Paranoia](#chapter-4-pragmatic-paranoia)
  - [23. DBC: Design by Contract](#23-dbc-design-by-contract)
    - [Implementing DBC](#implementing-dbc)
    - [Assertions](#assertions)
    - [DBC And Crashing Early](#dbc-and-crashing-early)
    - [Semantic Invariant](#semantic-invariant)
    - [Dynamic Contracts And Agents](#dynamic-contracts-and-agents)
  - [24. Dead Programs Tell No Lies](#24-dead-programs-tell-no-lies)
    - [Crash, Don't Trash](#crash-dont-trash)
  - [25. Assertive Programming](#25-assertive-programming)
    - [Assertions And Side Effects](#assertions-and-side-effects)
    - [Leave Assertions Turned On](#leave-assertions-turned-on)
  - [26. How to Balance Resources](#26-how-to-balance-resources)
    - [Balancing And Exception](#balancing-and-exception)
      - [**An Exception Antipattern**](#an-exception-antipattern)
    - [When You Can't Balance Resources](#when-you-cant-balance-resources)
      - [Checking The Balance](#checking-the-balance)
  - [26. Don’t Outrun Your Headlights](#26-dont-outrun-your-headlights)
    - [Black Swans](#black-swans)
<!-- /TOC -->
# Chapter 1. A Pragmatic Philosophy

## 1. The Cat Ate My Source Code
>💡 **Tip: Provide Options, Don't Make Lame Excuses**  

Instead of giving excuses, present possible options. Instead of saying that something cannot be done, explain what can be done to improve the situation.

## 2. Software Entropy

>💡 **Tip: Don't Live with Broken Windows**  

When a broken window is not promptly repaired, it creates a feeling of neglect among the building's occupants. They perceive that those in charge don't care about the building. As a result, more windows get broken, litter starts accumulating, and graffiti appears. Eventually, the building suffers significant structural damage. Within a short period, the damage becomes so severe that the owner no longer wants to fix it, confirming the initial sense of abandonment.

## 3. Stone Soup and Boiled Frogs
>💡 **Tip: Be a Catalyst for Change**  

In the story of Stone Soup, a group of clever travelers initiates the making of a stone soup when they encounter a village where no one is willing to share their food. They start by boiling a pot of water and adding a simple stone. Curiosity piques among the villagers, and the travelers suggest that the soup would taste even better with some vegetables. Each villager adds something, such as vegetables or spices, and as the soup cooks, the aroma entices even more people to join in. Eventually, a hearty and nourishing soup is enjoyed by everyone, demonstrating the power of collaboration and sharing.

It's time to bring out the stones. Work out what you can reasonable ask for. Develop it and demo it to others, let them admire. Then say "of course, it would be better if we added..."

_'People find it easier to join an ongoing success'_

>💡 **Tip: Remember the Big Picture**  

If a frog is put directly into boiling water, it will immediately jump out to escape the heat. However, if the frog is placed in cool water and the temperature is gradually increased, the frog won't realize the danger and will stay in the water until it becomes too hot and is eventually cooked.

Don't be like a frog. Keep an eye on the big picture.

## 4. Good enough soup
>💡 **Tip: Make Quality a Requirements Issue**  

The scope and quality of the system should be specified as part of that system's requirements.

**Know When to Stop**  
An art is ruined if the painter doesn't know when to stop. Don't spoil a perfectly good code by over embellishment and over-refinement. Move on and let your code stand on its own for a while.

## 5. Your Knowledge Portfolio
_An investment in knowledge always pays the best interest._

Manage your knowledge portfolio similar to the financial portfolio
### Building Your Portfolio
* Invest regularly
* Diversify
* Manage risk
* Buy low, sell High
* Review and rebalance

>💡 **Tip: Invest Regularly in Your Knowledge Portfolio**

### Goals
* Learn at least one new language every year
* Read a technical book each quarter
* Read nontechnical books too
* Take classes
* Participate in local user groups
* Experiment with different environments
* Stay current
* Get wired

>💡 **Tip: Critically Analyze What You Read and Hear**  

It is essential to guarantee that the knowledge in your portfolio remains accurate and unbiased, unaffected by either vendor or media hype.

## 6. Communicate
>💡 **Tip: It's Both What You Say and the Way You Say It**  

The more effective the communication, the more influential you become
* Know your audience and tickle their interest
* Choose your moment:  Understanding when your audience needs to hear your information
* Make it look good: Add good-looking vehicle to your important ideas and engage your audience
* Be a listener: Encourage people to talk by asking questions


# Chapter 2. A Pragmatic Approach

## 7. The Evils of duplication

>💡 **Tip: DRY-Don't repeat yourself**  

DRY principle: Every piece of knowledge must have a single, unambiguous, authoritative representation within a system  

How does duplication arise?  

* **Imposed duplication**  

    Developers feel they have no choice—the environment seems to require duplication.
  * **Multiple representations of information**  
eg. client-server application using different languages on client. Or a class whose attributes mirror the schema of a database table.  
Solution: Often answer is to write a simple filter or a code generator. Structures in multiple languages can be built from a common metadata representation using a simple code generator each time the software is being built. Class definitions could be generated automatically from the online database schema, or from the metadata used to build the schema in the first place.

  * **Documentation in Code**  
DRY principle tells us to keep low-level knowledge in code, where it belongs, and reserve the comment for high-level explanations. Otherwise, we are duplicating knowledge, and every change means changing both the code and comments. The comments will become outdated and untrustworthy comments are worse than no comments at all.

  * **Documentation and Code**  
With deadlines looming and important clients clamoring, we tend to defer the updating of documentation  

  * **Language Issue**  
Often languages impose of modules interface with its implementation, resulting in duplication. C and C++ have header files that duplicate names and type information of exported variables, functions and classes. In such cases, there is no point in duplicating a function and class header comments between two files. Use header files to document the interface issues and implementation files to document the nitty-gritty details that users of your code dont need to know.

* **Inadvertent duplication**  

    Developers don't realize that they are duplicating information.  
    Sometimes, duplication comes from mistakes in the implementation of design.  
    Eg. Multiple data elements that are mutually dependent  
    Consider the code below:

    ```cpp
        class Line {
            public: 
                Point start;
                Point end;
                double length;
        };
    ```  

    This might look reasonable as the line has a start, end and a length (even if its zero). But, we have duplication here.  
    Length is defined by start and end points, change in any value will result in changing the length. So its better to make length, a calculated field.

    ```cpp
        class Line {
            public:
                Point start;
                Point end;
                double length(){
                    return start.distanceTo(end);
                }
        };
    ```  

    Eventually, you may choose to violate the DRY principle for performance reasons. eg. for caching data to avoid repeating expensive operations. The trick is to localize the impact. The violation is not exposed to outside world: only methods within the class have to worry about keeping things straight.

    ```cpp
        class Line{
            private:
                bool changed;
                double length;
                Point start;
                Point end;
            public:
                void setStart(Point p) {start = p; changed = true;}
                void setEnd(Point p) {end = p; changed = true;}
                Point getStart(void){return start;}
                Point getEnd(void) {return end;}
                double getLength(){
                    if(changed){
                        length = start.distanceTo(end);
                        changed = false;
                    }
                    return length;
                }
        };
    ```

* **Impatient duplication**  
    Developers get lazy and duplicate because it seems easier.  
    Always remember, "shortcut makes long delays"  
    Impatient duplication is an easy form to detect and handle, but it takes discipline and a willingness to spend time up front to save pain later.

* **Interdeveloper duplication**  
    Multiple people on a team (or on different teams) duplicate a piece of information.  
    It is the hardest type of duplication to detect and handle. Entire set of functionalities may be duplicated and that duplication may go undetected for years, leading to maintenance problems.  
    Deal with this problem by having a clear design, a strong technical project leader. However, at the module level, the problem is more insidious. Commonly needed functionality or data that doesn't fall into an obvious area of responsibility can be implemented many times over. Best way to deal with this is to encourage active communication between developers.  
    "Make your code easy to reuse", if it isn't easy, people wont reuse it.  
    >💡 **Tip 12: Make it easy to reuse**  

## 8. Orthogonality

>💡 **Tip: Eliminate Effects Between Unrelated Things**  

Two or more systems are orthogonal if the changes in one system doesn't affect the other system. i.e. Loosely coupled  
Benefits:

* Gain productivity  
Changes are localized, so development time and testing time are reduced. An orthogonal approach promotes reuse. If components have specific, well defined responsibilities, they can be combined with new components in ways that was not envisioned by its implementors. The more loosely coupled your systems, the easier it is to reconfigure and re-engineer.

* Reduce risk  
If a module is sick, it is less likely to spread the symptoms around the rest of the system. System will be better tested. You will not be tightly tied to a specific vendor, product, or platform, because the interfaces to these third party components will be isolated.

* Ways in which orthogonality can be applied
  * Project teams
    When teams are organized with lots of overlap, members are confused about responsibilities. Every change needs a meeting of the entire team, because any one of them might be affected. How do you organize? No simple answer as it is dependent on various factors. Preference is to start by separating infrastructure from application. eg. Database, communications interface, middleware layer, and so on gets its own sub team.

    Litmus test: See how many people need to be involved in discussing each change that is requested. The larger the number, the less orthogonal the group. An orthogonal team is more efficient. (However, communication among the sub teams should be encouraged)

  * Design  
    Systems should be composed of a set of cooperating modules, each of which implements a functionality independent of others. Sometimes these components are organized as layers, each providing a level of abstraction. Here, each layer uses only the abstraction provided by the layer below it, allows great flexibility to change underlying implementation without affecting code.

    Litmus test: Once components are mapped, ask yourself, 'If I dramatically change the requirements behind a particular function, how many modules are affected?' In an orthogonal system, ideally the answer should be one. eg: Moving a button on UI should not require a change in the database schema.

  * Toolkits and Libraries
    When you bring in a toolkit or even a library from other member of your team, ask yourself whether it imposes changes on your code that shouldn't be there. If an object persistence scheme is transparent, then its orthogonal. If it requires you to create or access objects in a special way, then its not. Keeping such things isolated from your code has the added benefit of making it easy to change vendors in the future.

  * Coding
    1. Keep your code decoupled : write shy code, modules that don't reveal anything unnecessarily and don't rely on other module implementation
    2. Avoid global data: Risk of being tied to other components that share that data. Even globals for reading values can lead to trouble once you change your code to be multithreaded. Rather pass any required context to your modules.
    3. Avoid similar functions: Often you will come across a set of functions that share common code at start and end, but has different central algorithm. Use 'strategy' design pattern for a better implementation.  

  * Testing
    Orthogonal system is easy to test. Litmus test: What does it take to link and build a unit test? If you need to drag a large part of system to compile or link a unit test, then the system is not well decoupled. Bug fixing is another example, see how local the change needed to fix the bug is.

## 9. Reversibility

>💡 **Tip: There are no Final Decisions**

Be prepared for changes. However, by sticking to DRY principle, decoupling and use of metadata, we don't need to make as many critical, irreversible decisions.

* Flexible Architecture
Think about it up front, that you can support client-server, stand alone, or n-tier model just by changing a configuration file. Normally you can simply hide a third-party product behind a well defined abstract interface. But suppose you couldn't isolate it that cleanly. What if you had to sprinkle certain statements liberally through the code? Put that requirement in metadata, and use some automatic mechanism such as Perl or Aspects, to insert the necessary statements in the code itself. Whatever mechanism you use, make it reversible.

## 10 Tracer Bullets

>💡 **Tip: Use Tracer Bullets to Find the Target**

Tracer code contains all the error checking, structuring, documentation, and self-checking that any piece of production code has. It simply is not fully functional. However, once you have achieved end-to-end connection among the components of your system, you can check how close to the target you are, adjusting if necessary. Once you're on target, adding functionality is easy.  

Advantages:
  - Users get to see something working early
  - Developers build a structure to work in
  - You have an integration platform
  - You have something to demonstrate
  - You have a better feel for progress  

### Tracer Bullets Don't Always Hit Their Target  

- Tracer bullets show what you're hitting. This may not always be the target. You then adjust your aim until they're on target. That's the point.  
It's the same with tracer code. You use the technique in situations where you're not 100% certain of where you're going. You shouldn't be surprised if your first couple of attempts miss. Work out how to change what you've got to bring it nearer the target and be thankful that you've used a lean development methodology.

### Tracer Code versus Prototyping

- With a prototype, you're aiming to explore specific aspects of the final system.
Tracer code is used to know how the application as a whole hangs together. It provides an architectural skeleton for the developers to hang code.  

- Prototyping generates disposable code.
Tracer code is lean but complete, and forms part of the skeleton of the final system.

## 11. Prototypes and Post-it Notes

Prototypes are designed to answer just a few questions, so they are much cheaper and faster to develop than applications that go into production. But if you find yourself in an environment where you cannot give up the details, then you need to ask yourself if you are really building a prototype at all.  

### Things to Prototype  

Anything that carries risk, hasn’t been tried before, or that is absolutely critical to the final system, unproven, experimental, or doubtful.

- Architecture  
- New functionality in an existing system
- Structure or contents of external data
- Third-party tools or components
- Performance issues
- User interface design  

>💡 **Tip: Prototype to learn**  

### How to Use Prototypes  

Avoid details when building a prototype  

- Correctness: Use dummy data wherever possible  
- Completeness: The prototype may function only in a very limited sense  
- Robustness: Error checking is likely to be incomplete or missing entirely  
- Style: It's painful to admit, but prototype code probably doesn't have much in way of comments or documentation  

### Prototyping Architecture  

You may not even need to code in order to prototype architecture—you can prototype on a whiteboard, with Post-it notes or index cards. What you are looking for is how the system hangs together as a whole, again deferring details.  

Areas to look for in the architectural prototype  

- Are the responsibilities of the major components well defined and appropriate?
- Are the collaborations between major components well defined?
- Is coupling minimized?
- Can you identify potential sources of duplication?
- Are interface definitions and constraints acceptable?
- Does every module have an access path to the data it needs during execution? Does it have that access when it needs it?

Note: If you are investigating absolute (instead of relative) performance, you will need to stick to a language that is close in performance to the target language.  

### How Not to Use Prototypes  

Before you embark on any code-based prototyping, you must make it very clear that this code is disposable, incomplete, and unable to be completed.  

If you feel there is a strong possibility in your environment or culture that the purpose of prototype code may be misinterpreted, you may be better off with the tracer bullet approach. You’ll end up with a solid framework on which to base future development.

**Never deploy a prototype**  


## 14. Domain Languages  

>💡 **Tip: Program Close to the Problem Domain**  


## 15. Estimating  

>💡 **Tip: Estimate to Avoid Surprises**  

### How Accurate Is Accurate Enough?  

|  Duration    | Quote Estimate in                    |
|:-------------|:-------------------------------------|
| 1 - 15 days  | Days                                 |
| 3 - 6 weeks  | Weeks                                |
| 8 - 20 weeks | Months                               |
| 20+ weeks    | Think hard before giving an estimate |  

### Where Do Estimates Come From?
Ask someone who's been in a similar situation in the past.

- Understand What's Being Asked
- Build a Model of the System
- Break the Model into Components
- Give Each Parameter a Value
- Calculate the Answers
- Keep Track of Your Estimating Prowess  

### Estimating Project Schedules  

- Check requirements
- Analyze risk (and prioritize riskiest items earlier)  
- Design, implement, integrate  
- Validate with the users  

>💡 **Tip: Iterate the Schedule with the Code**  

Unless you are doing an application similar to a previous one, with the same team and the same technology, you’d just be guessing.  
So you complete the coding and testing of the initial functionality and mark this as the end of the first iteration. Based on that experience, you can refine your initial guess on the number of iterations and what can be included in each.  

### What To Say When Asked For An Estimate  

**You say "I'll get back to you"**  

You almost always get better results if you slow the process down and spend some time going through the steps we describe above.  
Estimates given at the coffee machine will (like the coffee) come back to haunt you.  

### Challenges
Start keeping a log of your estimates. For each, track how accurate you turned out to be. If your error was greater than 50%, try to find out where your estimate went wrong.  

<!-- New Version henceforth -->

# Chapter 3. The Basic Tools  


## 16. The Power of Plain Text  

>💡 **Tip: Keep Knowledge in Plain Text**  

Plain text doesn’t mean that the text is unstructured; HTML, JSON, YAML, and so on are all plain text.  

Advantages:  

- Insurance against obsolescence  
- Leverage existing tools
- Easier testing  

## 17. Shell Games  

>💡 **Tip: Use the Power of Command Shells**  

Invest some energy in becoming familiar with your shell and things will soon start falling into place. Play around with your command shell, and you’ll be surprised at how much more productive it makes you.  

### A Shell of your own  


You’ll spend a lot of time living in one of these shells. Be like a hermit crab and make it your own home.  

Shell customizations:  

- Setting color themes  
- Configuring a prompt  
- Aliases and shell functions  
  - Maybe you regularly update your Linux box, create an alias

    ```shell
    alias apt-up='sudo apt-get update && sudo apt-get upgrade'
    ```

- Command completion

## 18. Power Editing  

>💡 **Tip: Achieve Editor Fluency**  

The major gain is that by becoming fluent, you no longer have to think about the mechanics of editing. The distance between thinking something and having it appear in an editor buffer drop way down. Your thoughts will flow, and your programming will benefit.

### What Does “Fluent” Mean?

Here’s the challenge list  
Can you do all this without using a mouse/trackpad?

- When editing text, move and make selections by character, word, line, and paragraph
- When editing code, move by various syntactic units (matching delimiters, functions, modules, etc)
- Reindent code following changes
- Comment and uncomment blocks of code with a single command
- Undo and redo changes
- Split the editor window into multiple panels, and navigate between them
- Navigate to a particular line number. Sort selected lines
- Search for both strings and regular expressions, and repeat previous searches
- Temporarily create multiple cursors based on a selection or on a pattern match, and edit the text at each in parallel
- Display compilation errors in the current project. Run the current project’s tests

### MOVING TOWARD FLUENCY  

Every time you find yourself doing something repetitive, find a better way to do it. Install it in your muscle memory by repeating it.

### Growing your editor  

When you bump into some apparent limitation of the editor, search for an extension to do the job.  

## 19. Version Control  

>💡 **Tip: Always Use Version Control**  

**Shared Directories Are Not Version Control** 

Even if you are a single-person team on a one-week project. Even if it’s a “throw-away’’ prototype. Even if the stuff you’re working on isn’t source code. Make sure that everything is under version control.  

### Version Control As A Project Hub  

Many teams have their VCS configured so that a push to a particular branch will automatically build the system, run the tests, and if successful deploy the new code into production.  
Sound scary? Not when you realize you’re using version control. You can always roll it back.

## 20. Debugging  

No one writes perfect software, so it’s a given that debugging will take up a major portion of your day.  

### Psychology Of Debugging  

>💡 **Tip: Fix the Problem, Not the Blame**  

Embrace the fact that debugging is just problem solving, and attack it as such.  
It doesn’t really matter whether the bug is your fault or someone else’s. It is still your problem.  

### A Debugging Mindset

Above all, remember the first rule of debugging:
>💡 **Don't Panic**  

Don’t waste a single neuron on the train of thought that begins “but that can’t happen” because quite clearly it can, and has.  
Resist the urge to fix just the symptoms you see: Always try to discover the root cause of a problem


### Where To Start  

Before you start to look at the bug, make sure that you are working on code that built cleanly—without warnings.  
When trying to solve any problem, you need to gather all the relevant data, its easy to be misled by coincidences.

- You may need to interview the user who reported the bug in order to gather more data than you were initially given  
- You must brutally test both boundary conditions and realistic end-user usage patterns. You need to do this systematically  

### Debugging Strategies  

#### **Reproducing Bugs**  

The best way to start fixing a bug is to make it reproducible.  
We want a bug that can be reproduced with a single command. It’s a lot harder to fix a bug if you have to go through 15 steps to reproduce it.  

So here’s the most important rule of debugging:
>💡 **Tip: Failing Test Before Fixing Code**  


#### **Code In A Strange Island**


All this talk about isolating the bug is fine, when faced with 50,000 lines of code and a ticking clock, what’s a poor coder to do?  
>💡 **Tip: Read the Damn Error Message**  

#### **Bad Results**

Get in there with a debugger and use your failing test to trigger the problem.  
Make sure you know how to move up and down the call stack and examine the local stack environment.  

Sometimes you’re looking at a stack trace that seems to scroll on forever. In this case, there’s often a quicker way to find the problem than examining each and every stack frame: use a **binary chop.** But before we discuss that, let’s look at two other common bug scenarios.  

#### **Sensitive To Input Values**

You can try looking at the place it crashes and work backwards.  
Get a copy of the dataset and feed it through a locally running copy of the app, making sure it still crashes.  
Then binary chop the data until you isolate exactly which input values are leading to the crash.  

#### **The Binary Chop**  

Binary Chop or Binary Search is a divide and conquer approach.

Choose a value in the middle of the array. If it’s the one you’re looking for, stop. Otherwise you can chop the array in two. If the value you find is greater than the target then you know it must be in the first half of the array, otherwise it’s in the second half. Repeat.  

Let’s see how to apply it to debugging:

- When you’re facing a massive stacktrace and you’re trying to find out exactly which function mangled the value in error
- If you find bugs that appear on certain datasets, split the dataset into two, and see if the problem occurs  
- If your team has introduced a bug during a set of releases, you can use the same type of technique.  

#### **Logging and/or Tracing**  

Seeing a stack trace can only tell you how you got here directly.  
You can use tracing statements to drill down into the code. That is, you can add tracing statements as you descend the call tree.  
Trace messages should be in a regular, consistent format as you may want to parse them automatically.  

#### **Rubber Ducking**  

A useful technique for finding the cause of the problem is to explain it to someone else.  
In explaining the problem to another person you must explicitly state things that you may take for granted when going through the code yourself. By having to verbalize some of these assumptions, you may suddenly gain new insight into the problem.  
Don't have a person to explain to? A rubber duck will do.

#### **Process Of Elimination**  

It is possible that a bug exists in the OS, the compiler, or a third- party product—but this should not be your first thought.  
It is much more likely that the bug exists in the application code under development.  
Even if the problem does lie with a third party, you’ll still have to eliminate your code before submitting the bug report.  

#### **The Element Of Surprise**  

>💡 **Tip: Don’t Assume It—Prove It**  

When faced with a “surprising’’ failure, you must accept that one or more of your assumptions is wrong.  
When you come across a surprise bug, beyond merely fixing it, you need to determine why this failure wasn’t caught earlier.
Consider whether you need to amend the unit or other tests so that they would have caught it.  
Make sure that whatever happened, you’ll know if it happens again.  

#### **DEBUGGING CHECKLIST**  

- Is the problem being reported a direct result of the underlying bug, or merely a symptom?
- Is the bug really in the framework you’re using? Is it in the OS? Or is it in your code?
- If you explained this problem in detail to a coworker, what would you say?
- If the suspect code passes its unit tests, are the tests complete enough? What happens if you run the tests with this data?
- Do the conditions that caused this bug exist anywhere else in the system? Are there other bugs still in the larval stage, just waiting to hatch?  

## 21. Text Manipulation  

>💡 **Tip: Learn a Text Manipulation Language**  

Using these languages, you can quickly hack up utilities and prototype ideas—jobs that might take five or ten times as long using conventional languages.  

## 22. Engineering Daybooks  

Use journals to take notes in meetings, to jot down what you’re working on, to note variable values when debugging, to leave reminders where you put things, to record wild ideas, and sometimes just to doodle.  


# Chapter 4. Pragmatic Paranoia  

>💡 **Tip: You Can’t Write Perfect Software**  

Did that hurt? It shouldn’t. Embrace it. Celebrate it.  
No one in the brief history of computing has ever written a piece of perfect software.
Pragmatic Programmers don't trust themselves, either.

## 23. DBC: Design by Contract  

A correct program is one that does no more and no less than it claims to do.  

Use:

- Preconditions
  - What must be true in order for the routine to be called; the routine’s requirements
  - A routine should never get called when its preconditions would be violated
  - It is the caller’s responsibility to pass good data
- Postconditions
  - What the routine is guaranteed to do; the state of the world when the routine is done
- Invariants
  - A class ensures that this condition is always true from the perspective of a caller

>💡 **Tip: Design with Contracts**  

A contract between a routine and any potential caller can thus be read as:  
If all the routine’s preconditions are met by the caller, the routine shall guarantee that all postconditions and invariants will be true when it completes  

Write "lazy" code: be strict in what you will accept before you begin, and promise as little as possible in return.  

Remember, if your contract indicates that you’ll accept anything and promise the world in return, then you’ve got a lot of code to write!  

### Implementing DBC  

Simply enumerating at design time:

- What the input domain range is
- What the boundary conditions are
- What the routine promises to deliver (and what it doesn't)

### Assertions  

You can use assertions to apply DBC in some range. (Assertions are not propagated in subclasses)  

### DBC And Crashing Early  

It’s much easier to find and diagnose the problem by crashing early, at the site of the problem.  

### Semantic Invariant  

The error should be on the side of not processing a transaction rather than processing a duplicate transaction.  

### Dynamic Contracts And Agents  

Next time you design a piece of software, design its contract as well.  

## 24. Dead Programs Tell No Lies  

Pragmatic Programmers tell themselves that if there is an error, something very, very bad has happened.  

Note: Each and every case/switch statement needs to have a default clause: we want to know when the “impossible” has happened.  

>💡 **Tip: Crash Early**  

### Crash, Don't Trash  

Defensive programming is a waste of time. Let it crash!  
A dead program normally does a lot less damage than a crippled one.  

## 25. Assertive Programming  

>💡 **Tip: Use Assertions to Prevent the Impossible**  

Whenever you find yourself thinking “but of course that could never happen,” add code to check it. The easiest way to do this is with assertions.  

### Assertions And Side Effects  

It’s embarrassing when the code we add to detect errors actually ends up creating new errors. This can happen with assertions if evaluating the condition has side effects.  

### Leave Assertions Turned On  

There is a common misunderstanding about assertions. It goes something like this:  

- Assertions add some overhead to code. Because they check for things that should never happen, they’ll get triggered only by a bug in the code. Once the code has been tested and shipped, they are no longer needed, and should be turned off to make the code run faster.  

There are two patently wrong assumptions here.  

- First, testing finds all the bugs
- Second, the optimists are forgetting that your program runs in a dangerous world. During testing, someone playing a game won’t exhaust memory, and log files won’t fill the storage partition. These things might happen when your program runs in a production environment.  

Even if you do have performance issues, turn off only those assertions that really hit you.  

## 26. How to Balance Resources  

>💡 **Tip: Finish What You Start**  

The function or object that allocates a resource should be responsible for deallocating it  

>💡 **Tip: Act Locally**  

When in doubt, it always pays to reduce scope  

### Balancing And Exception  

If an exception is thrown, how do you guarantee that everything allocated prior to the exception is tidied up?  
You generally have two choices:  

- Usevariablescope(forexample,stackvariablesinC++orRust)  
- Useafinallyclauseinatry...catchblock  

#### **An Exception Antipattern**

Can you see what’s wrong?

```java
begin
    thing = allocate_resource()
    process(thing)
finally
    deallocate(thing)
end
```  

What happens if the resource allocation fails and raises an exception? The finally clause will catch it, and try to deallocate a thing that was never allocated.  

The correct pattern:  

```java
thing = allocate_resource()
begin
    process(thing)
finally
    deallocate(thing)
end  
```  

### When You Can't Balance Resources  

There are times when the basic resource allocation pattern just isn’t appropriate.  
One routine will allocate an area of memory and link it into some larger structure, where it may stay for some time.  

You have three main options:  

- The top-level structure is also responsible for freeing any substructures that it contains. These structures then recursively delete data they contain, and so on.
- The top-level structure is simply deallocated. Any structures that it pointed to (that are not referenced elsewhere) are orphaned.
- The top-level structure refuses to deallocate itself if it contains any substructures.  

#### Checking The Balance  

It is always a good idea to build code that actually checks that resources are indeed freed appropriately


## 26. Don’t Outrun Your Headlights  

>💡 **Tip: Take Small Steps—Always**  

Always take small, deliberate steps, checking for feedback and adjusting before proceeding.  
What do we mean exactly by feedback?  

- Results in a REPL provide feedback on your understanding of APIs and algorithms
- Unit tests provide feedback on your last code change
- User demo and conversation provide feedback on features and usability  

What’s a task that’s too big? Any task that requires “fortune telling.”

### Black Swans  

>💡 **Tip: Avoid Fortune-Telling**  

In his book, The Black Swan, Nassim Nicholas Taleb posits that all significant events in history have come from high-profile, hard- to-predict, and rare events that are beyond the realm of normal expectations.  

These outliers, while statistically rare, have disproportionate effects.

Content from The Pragmatic Programmer, by Andrew Hunt and David Thomas. Visit [www.pragmaticprogrammer.com](http://www.pragmaticprogrammer.com).
Copyright 2000 by Addison Wesley Longman, Inc.