# The Pragmatic Programmer
There are the notes that I'm writing while reading The Pragmatic Programmer by Andy Hunt and Dave Thomas.

## Preface

### Characteristics of a Pragmatic Programmer

- Early adopter
- Inquisitive (curious)
- Critical thinker
- Realist (ability to accurately estimate difficulty of a task)
- Jack of all trades
- Care about the craft
- Think all the time (never go on autopilot)
- Responsible (hold yourself accountable)
- Holistic approach to problem solving

### Individuality and craftsmanship in engineering

Much like the techniques used by stonecutters seem archaic in our time, the engineering techniques we use will be outdated in the future. Still, our craftsmanship will be remembered, in the same way we admire the craftsmanship and dedication of each stonecutter who contributed to the construction of large cathedrals.

### Small improvements

Small improvements every day often make the most difference. Every day, the Pragmatic Programmer works to refine his existing skills and expand his repertoire.

## A Pragmatic Philosophy

### Technical Debt

Research shows that the presence of a single broken window in a building can be the turning point leading to the building being abandoned. Hopelessness can be incredibly contagious. A single broken window, left unfixed for too long, can instill the idea that perhaps nothing can be fixed.

When technical debt is found in a project, fix it, or at least mark it as something that must be fixed.

### A glimpse of the possibility

When working in a team, it is often hard to convince others to implement a feature or a change. Make a good demo, and they will marvel at the possibilities and be more willing to cooperate. 

People find it easier to join an ongoing success.

### Quality as a requirements issue

Determine the quality of software required in a project. A pragmatic solution should take into account that not all software must be perfect.

## Knowledge is an investment

Learning is an investment. Some investments have better returns than others.

### Rules of thumb

- Invest regularly
- Diversify
- High risk and low risk
- Review portfolio regularly

### Goals

- One technical book every month
- One new language every year
- Read blogs about the newest technologies
- Experiment with different tools
- Participate in local meetups

### Opportunities

- Always keep a book with you, so you can spend any loose time reading.
- When asked a question that you don't know the answer of, admit to it and extensively research until you find the answer. Then, get back to the person to output the information.
- If you cannot find the answer, find who can.

## A Pragmatic Approach

### ETC (Easier to change)

All design principles are ways to implement easier to change code. Every time you implement a change, think about whether the change you implemented made the overall system easier or harder to change.

### DRY (Don't repeat yourself)

Don't duplicate knowledge. Write code so that when knowledge (including functionality) must be changed, you only have to make that change once, at one location.

This rule can be applied to documentation and comments as well. Write comments to explain why something was implemented a particular way, not how (since the code already conveys how the functionality is implemented).

Duplication of knowledge is sometimes a necessary evil when optimizing for performance. The trick here is to localize the impact of the violation: when caching data to minimize repeating expensive operations in a class, for example, make sure that the interface of the class does not reveal the fact that it is caching values.

### Orthogonality

Write modular code that does one thing well in isolation, and structure your components so that they are as little interlinked as possible. As long as a component's public interface has not been changed, a change in it's code should not affect any other components.

Modules that only reveal what is absolutely necessary in it's public interface is less likely to have unecessary coupling with other modules.

### Reversibility

Hide external APIs with your own abstraction layers. This makes it easier to switch third-party products, like databases and UI frameworks.

### Build the skeleton first

Instead of developing each module of the project one at a time and connecting them once they are completely implemented, build the skeleton of the software first, and then incrementally improve and augment the modules.

- Easier to change the requirements
- Allows adjusting of the overall structure if it doesn't "hit the target"
- See the big picture from the start
- Better feel for progress

Unlike prototypes, the skeleton is not disposable, so it should be kept up to the same standards as the rest of the code.

### Prototypes

Prototypes focus on a specific aspect of the system. They are disposable, and comprise on robustness (no error checking), style (no documentation), correctness (dummy data is sometimes used), and completeness (severely lacks features).

The right tool should be used to save time and resources. Prototypes need not be code-based: software architecture and UI can be prototyped on a whiteboard, for instance.

### Domain languages

You can design a domain language so that you can code close to the problem domain. Some domain languages are "internal" (i.e., they are an extension of the language they're written in, created using macros and metaprogramming), whereas some are "external" (i.e., a parser was written for them).

Don't spend more effort than you save. Internal languages are sometimes worth implementing, but external languages are typically not worth creating.

### Estimating

If an estimate you made was wrong, try to identify what exactly was wrong about it so you can learn to estimate better.

Most estimates are not just a single number: the full story includes multiple estimates along with their respective scenarios. Think of an optimistic, a most likely, and a pessimistic estimate.

## The Basic Tools

### Plain Text

Plain text is superior to binary formats because it is self-describing and human-readable. It will survive long after the software that wrote it is gone.

### Shell

The shell is the pragmatic programmer's workbench. Shells are much more powerful than GUIs: take some time learning how to use the many poweful commands. Customize your shell to your liking.

### Editor fluency

Becoming fluent with your editor will allow it to become an extension of your mind.

Learn to do the following without using a mouse:
- Move, select and delete characters, words, lines, and blocks
- Move, select and delete by various syntaxic units such as functions, classes and modules
- Comment and uncomment blocks of code
- Undo and redo changes
- Split into multiple windows and switch between them
- Switch between tabs
- Navigate to a particular line number
- Search by string or regular expression
- Display errors

Stop using your mouse and keep your hands on the keyboard.

### Version Control

Put everything under VCS, including all of your project and your configuration files. If your computer fails one day, you should be able to easily set a new one up using all the configuration files you put under VCS. 

### Debugging

Binary chops can often be invaluable in isolating where the root of the issue is. One can binary chop a deep stack trace, a dataset to find the offending value, and even commits in a VCS to find where and when the issue first appeared.

Not understanding the cause of a bug is a result of a wrong assumption you are making. Don't assume that a piece of code is working: prove it in these specific circumstances. Explaining the issue to someone else (or a rubber duck) can often help you identify the faulty assumption.

After fixing a bug, think about why the bug wasn't identified earlier, what made it happen in the first place, and how you can avoid repeating the same mistake in the future.

### Automation

Automate common tasks with a tool like Python, and get good at it. You can save a lot of time in the long run by doing this.

### Engineering daybook

Take notes of everything you do or think. When you have an idea that isn't immediately relevant to the task at hand, write it down so that you can keep focusing on what you're doing now without forgetting the idea. Writing down what you are doing when debugging, for example, can help you brain switch gears and realize what's wrong.

## Pragmatic Paranoia

### Design by Contract

Establish preconditions and postconditions in each function. Think about class invariants and document them. In languages that do not implement them natively, use assertions to enforce preconditons and postconditions. Assertions do not completely implement Design by Contract however, especially in object-oriented languages because assertions in methods do not propagate down the inheritance hierarchy.

### Crash early

Put assertions everywhere and never assume that anything is impossible. It is much easier to debug an early crash due to an assertion than unexpected behaviour caused by an issue that happened millions of instructions before.

Keep these assertions in production. You can even provide a nice UI for when a crash occurs, to make it easier for the users to report the bug. Many issues only happen in production (i.e., in the "real world"). If these assertions hinder performance, one can implement multiple "levels" of assertions so that only the most expensive ones are disabled in production.
