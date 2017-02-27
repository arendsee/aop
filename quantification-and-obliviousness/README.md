# Quantification

A very heavily cited paper in the AOP world is `Aspect-oriented programming for
quantification and obliviousness` by Filman and Friedman.

Here is the abstract

```

    This paper proposes that the distinguishing characteristic of
    Aspect-Oriented Programming (AOP) systems is that they allow programming by
    making quantified programmatic assertions over programs written by
    programmers oblivious to such assertions. Thus, AOP systems can be analyzed
    with respect to three critical dimensions: the kinds of quantifications
    allowed, the nature of the actions that can be asserted, and the mechanism
    for combining base-level actions with asserted actions. Consequences of
    this perspective are the recognition that certain systems are not AOP and
    that some mechanisms are expressive enough to allow programming an AOP
    system within them. A corollary is that while AOP can be applied to
    Object-Oriented Programming, it is an independent concept applicable to
    other programming styles.

```

Below is essentially a paraphrasing rewrite of the paper. 

Programming language are a system for writing statements that compile into
instructions. Early languages were unitary and local. Unitary in that elements
in statements map to single effects in the final program. Local in that
elements nearby in the statement text are nearby in the instruction text. 

As languages have evolved, they have gained means of breaking locality and
unity. Functions break locality by separating calls and implementations, but
they are still unitary. Inheritance breaks unity as well. When a parent
function is altered, for example, all descendents calling this function are
altered as well. This is quantification.

A quantified change is a change in one location that has effects in many
locations.

However, super-sending OO languages, like Java and Smalltalk, are not
oblivious. The programmer of the derived class and the parent class need to
comply with a single convention. Oblivion comes when the parent class adds a
method and the children are altered without knowing it. This frees the
programmer of the derived class from needing to know about the parent. This
removes the meta-knowledge needed between parent and child.

The goal of AOP is to allow functionallity to be applied across sets of code
written by oblivious programmers.

AOP allows statements of the following form

```
In contexts P, where condition C is met, do action A
```

Implementing such statements requires consideration of three concepts:

 1. Quantification - what conditions C are allowed?

 2. Interface - how do actions A interact with base code?

 3. Weaving - how will the program perform condition checking and execution of A from within P?

Quantification can be static or dynamic.

Static quantification can be black-box or clear-box. Block-box implementations
are allow quantification across the interface, wrappers for exposed functions.
Clear-box implementation allows coupling to internals, for example matches to
code within the parse tree.
