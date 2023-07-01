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

>💡 **Tip: There are no Final Decisions.**

Be prepared for changes. However, by sticking to DRY principle, decoupling and use of metadata, we don't need to make as many critical, irreversible decisions.

* Flexible Architecture
Think about it up front, that you can support client-server, stand alone, or n-tier model just by changing a configuration file. Normally you can simply hide a third-party product behind a well defined abstract interface. But suppose you couldn't isolate it that cleanly. What if you had to sprinkle certain statements liberally through the code? Put that requirement in metadata, and use some automatic mechanism such as Perl or Aspects, to insert the necessary statements in the code itself. Whatever mechanism you use, make it reversible.



Content from The Pragmatic Programmer, by Andrew Hunt and David Thomas. Visit [www.pragmaticprogrammer.com](http://www.pragmaticprogrammer.com).
Copyright 2000 by Addison Wesley Longman, Inc.