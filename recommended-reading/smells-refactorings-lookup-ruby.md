# Format of this document

## Code Smell
_Smell Type_

> Smell description

- `[page number]` Refactorings _(Refactoring type)_

### Note about page numbers

Page numbers prefixed with a **`K`** refer to _[Refactoring to Patterns](https://www.amazon.com/Refactoring-Patterns-Joshua-Kerievsky/dp/0321213351)_, Joshua **K**erievsky.

Eg, `[K 137]` means page `137` in _Refactoring to Patterns_.

Page numbers prefixed with a **`F`** refer to _[Refactoring: Ruby Edtion](https://www.amazon.com/Jay-Fields-Refactoring-Addison-Wesley-Professional-dp-B008UYP4FE/dp/B008UYP4FE)_, by Martin **F**owler, et al.

Eg, `[F 369]` means page `369` in _Refactoring: Ruby Edtion_.

***
***
***

# Code smells and refactorings

## Alternative Classes with Different Interfaces

> Occurs when the interfaces of two classes are different and yet the classes are quite similar. If you can find the similarities between the two classes, you can often refactor the classes to make them share a common interface [F 83, K 43]

- `[K 247]` Unify Interfaces with Adapter _(Big Refactorings)_
- **`[F 298]` Rename Method _(Making Method Calls Simpler)_**
- **`[F 167]` Move Method _(Moving Features Between Objects)_**

***

## Case Statement

> This smell exists when the same case statement (or “if...else if...else if” statement) is duplicated across a system. Such duplicated code reveals a lack of object orientation and a missed opportunity to rely on the elegance of polymorphism. [F 80, K 44]

- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- `[K 320]` Move Accumulation to Visitor _(Big Refactorings)_
- `[K 191]` Replace Conditional Dispatcher with Command _(Big Refactorings)_
- **`[F 279]` Replace Conditional with Polymorphism _(Simplifying Conditional Expressions)_**
<!--- `[F 223]` Replace Type Code with Subclasses _(Organizing Data)_ -->
- **`[F 225]` Replace Type Code with Polymorphism _(Organizing Data)_**
- **`[F 239]` Replace Type Code with State/Strategy _(Organizing Data)_**
- **`[F 232]` Replace Type Code with Module Extension _(Organizing Data)_**
- **`[F 310]` Replace Parameter with Explicit Methods _(Simplifying Conditional Expressions)_**
- **`[F 284, K 301]` Introduce Null Object _(Simplifying Conditional Expressions)_**

***

## Combinatorial Explosion
_Big Smells_

A subtle form of duplication, this smell exists when numerous pieces of code do the same thing using different combinations of data or behavior. [K 45]

- `[K 269]` Replace Implicit Language with Interpreter _(Big Refactorings)_

***

## Comments (a.k.a. Deodorant)
_Class Smells_

When you feel like writing a comment, first try "to refactor so that the comment becomes superfluous" [F 85]

- **`[F 298]` Rename Method _(Making Method Calls Simpler)_**
- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 292]` Introduce Assertion _(Simplifying Conditional Expressions)_**

***

## Conditional Complexity
_Big Smells_

> Conditional logic is innocent in its infancy, when it’s simple to understand and contained within a few lines of code. Unfortunately, it rarely ages well. You implement several new features and suddenly your conditional logic becomes complicated and expansive. [K 41]

- **`[F 284, K 301]` Introduce Null Object _(Simplifying Conditional Expressions)_**
- `[K 144]` Move Embellishment to Decorator _(Big Refactorings)_
- `[K 129]` Replace Conditional Logic with Strategy _(Big Refactorings)_
- `[K 166]` Replace State-Altering Conditionals with State _(Big Refactorings)_

***

## Data Class
_Inter-Class Smells_

> Classes that have fields, getting and setting methods for the fields, and nothing else. Such classes are dumb data holders and are almost certainly being manipulated in far too much detail by other classes. [F 84]

- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 327]` Hide Method _(Making Method Calls Simpler)_**
- **`[F 219]` Remove Setting Method _(Organizing Data)_**
- **`[F 324]` Hide Method _(Making Method Calls Simpler)_**
<!-- - `[F 206]` Encapsulate Field _(Organizing Data)_ -->

***

## Data Clumps
_Inter-Class Smells_

> Bunches of data that that hang around together really ought to be made into their own object. A good test is to consider deleting one of the data values: if you did this, would the others make any sense? If they don't, it's a sure sign that you have an object that's dying to be born. [F 79]

- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- **`[F 313]` Preserve Whole Object _(Making Method Calls Simpler)_**
- **`[F 320]` Introduce Parameter Object _(Making Method Calls Simpler)_**

***

## Dead Code
_Class Smells_

- Delete Code

***

## Disjointed APIs
_Ruby specific code smell_

> Occurs when a library which provides flexibility, used in many different ways, presenting a fine-grained, disjointed API, with many configuration options. When one project does not use all of the configuration options, but reuses the same set of configuration in multiple places. [F 86]

- **`[F 346]` Introduce Expression Builder _(Making Method Calls Simpler)_**
- **`[F 341]` Introduce Gateway _(Making Method Calls Simpler)_**

***

## Divergent Change

> Occurs when one class is commonly changed in different ways for different reasons. Separating these divergent responsibilities decreases the chance that one change could affect another and lower maintenance costs. [F 77]

- **`[F 175]` Extract Class _(Moving Features Between Objects)_**

***

## Duplicated Code

> Duplicated code is the most pervasive and pungent smell in software. It tends to be either explicit or subtle. Explicit duplication exists in identical code, while subtle duplication exists in structures or processing steps that are outwardly different, yet essentially the same. [F76, K 39]

- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 357]` Extract Module _(Dealing with Generalization)_**
- **`[F 135]` Extract Surrounding Method _(Composing Methods)_**
- **`[F 372, K 205]` Form Template Method _(Dealing with Generalization)_**
- **`[F 284, K 301]` Introduce Null Object _(Simplifying Conditional Expressions)_**
- **`[F 353]` Pull Up Method _(Dealing with Generalization)_**
- **`[F 131]` Substitute Algorithm _(Composing Methods)_**
- `[K 340]` Chain Constructors _(Big Refactorings)_
- `[K 214]` Extract Composite _(Big Refactorings)_
- `[K 88]` Introduce Polymorphic Creation with Factory Method _(Big Refactorings)_
- `[K 224]` Replace One/Many Distinctions with Composite _(Big Refactorings)_
- `[K 247]` Unify Interfaces with Adapter _(Big Refactorings)_
<!-- - `[F 320]` Pull Up Field _(Dealing with Generalization)_ -->

***

## Feature Envy
_Inter-Class Smells_

> Data and behavior that acts on that data belong together. When a method makes too many calls to other classes to obtain data or functionality, Feature Envy is in the air. [F 78]

- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- **`[F 172]` Move Field _(Moving Features Between Objects)_**

***

## Freeloader (a.k.a. Lazy Class)
_Inter-Class Smells_

> A class that isn’t doing enough to pay for itself should be eliminated. [F 81, K 43]

- `[F 371]` Collapse Hierarchy _(Dealing with Generalization)_
- `[F 179]` Inline Class _(Moving Features Between Objects)_
- `[K 114]` Inline Singleton _(Big Refactorings)_

***

## Inappropriate Intimacy
_Inter-Class Smells_

> Sometimes classes become far too intimate and spend too much time delving into each others’ private parts. We may not be prudes when it comes to people, but we think our classes should follow strict, puritan rules. Over-intimate classes need to be broken up as lovers were in ancient days. [F 83]

- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- **`[F 172]` Move Field _(Moving Features Between Objects)_**
- **`[F 213]` Change Bidirectional Association to Unidirectional Association _(Organizing Data)_**
- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- **`[F 181]` Hide Delegate _(Moving Features Between Objects)_**
- **`[F 386]` Replace Inheritance with Delegation _(Dealing with Generalization)_**

***

## Incomplete Library Class

> Occurs when responsibilities emerge in our code that clearly should be moved to a library class, but we are unable or unwilling to modify the library class to accept these new responsibilities. [F 84]

- **`[F 167]` Move Method _(Moving Features Between Objects)_**
<!-- - `[F 162]` Introduce Foreign Method _(Moving Features Between Objects)_ -->
<!-- - `[F 164]` Introduce Local Extension _(Moving Features Between Objects)_ -->

***

## Inconsistent Name
_Name Smells_

- `[F 298]` Rename Method _(Making Method Calls Simpler)_
- Rename Field
- Rename Class

***

## Indecent Exposure
_Big Smells_

> This smell indicates the lack of what David Parnas so famously termed information hiding. The smell occurs when methods or classes that ought not to be visible to clients are publicly visible to them. Exposing such code means that clients know about code that is unimportant or only indirectly important. This contributes to the complexity of a design. [K 42]

- `[K 80]` Encapsulate Classes with Factory _(Big Refactorings)_

***

## Large Class
_Class Smells_

> Fowler and Beck note that the presence of too many instance variables usually indicates that a class is trying to do too much. In general, large classes typically contain too many responsibilities. [F 76, K 44]

- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- **`[F 357]` Extract Module _(Dealing with Generalization)_**
- **`[F 363]` Extract Subclass _(Dealing with Generalization)_**
<!-- - `[F 341]` Extract Interface _(Dealing with Generalization)_ -->
- `[F 191]` Replace Data Value with Object _(Organizing Data)_
- `[K 191]` Replace Conditional Dispatcher with Command _(Big Refactorings)_
- `[K 269]` Replace Implicit Language with Interpreter _(Big Refactorings)_
- `[K 166]` Replace State-Altering Conditionals with State _(Big Refactorings)_

***

## Lazy Class (a.k.a. Freeloader)
_Inter-Class Smells_

> A class that isn’t doing enough to pay for itself should be eliminated. [F 81, K 43]

- **`[F 371]` Collapse Hierarchy _(Dealing with Generalization)_**
- **`[F 179]` Inline Class _(Moving Features Between Objects)_**
- **`[F 262]` Inline Module _(Dealing with Generalization)_**
- `[K 114]` Inline Singleton _(Big Refactorings)_

***

## Long Method
_Class Smells_

> In their description of this smell, Fowler and Beck explain several good reasons why short methods are superior to long methods. A principal reason involves the sharing of logic. Two long methods may very well contain duplicated code. Yet if you break those methods into smaller methods, you can often find ways for the two to share logic. Fowler and Beck also describe how small methods help explain code. If you don’t understand what a chunk of code does and you extract that code to a small, well-named method, it will be easier to understand the original code. Systems that have a majority of small methods tend to be easier to extend and maintain because they’re easier to understand and contain less duplication. [F 74, K 40]

- **`[F 102]` Extract Method _(Composing Methods)_**
- `[K 123]` Compose Method _(Big Refactorings)_
- **`[F 261]` Decompose Conditional _(Simplifying Conditional Expressions)_**
- **`[F 320]` Introduce Parameter Object _(Making Method Calls Simpler)_**
- `[K 313]` Move Accumulation to Collecting Parameter _(Big Refactorings)_
- `[K 320]` Move Accumulation to Visitor _(Big Refactorings)_
- **`[F 313]` Preserve Whole Object _(Making Method Calls Simpler)_**
- `[K 191]` Replace Conditional Dispatcher with Command _(Big Refactorings)_
- `[K 129]` Replace Conditional Logic with Strategy _(Big Refactorings)_
- **`[F 127]` Replace Method with Method Object _(Composing Methods)_**
- **`[F 111]` Replace Temp with Query _(Composing Methods)_**
- **`[F 114]` Replace Temp with Chain _(Composing Methods)_**

***

## Long Parameter List
_Class Smells_

> Long lists of parameters in a method, though common in procedural code, are difficult to understand and likely to be volatile. Consider which objects this method really needs to do its job - it's okay to make the method to do some work to track down the data it needs. [F 76]

- **`[F 317]` Replace Parameter with Method _(Making Method Calls Simpler)_**
- **`[F 320]` Introduce Parameter Object _(Making Method Calls Simpler)_**
- **`[F 142]` Introduce Named Parameter _(Composing Methods)_**
- **`[F 313]` Preserve Whole Object _(Making Method Calls Simpler)_**

***

## Magic Number
_Class Smells_

- `[F 217]` Replace Magic Number with Symbolic Constant _(Organizing Data)_

***

## Message Chains
_Inter-Class Smells_

> Occur when you see a long sequence of method calls or temporary variables to get some data. This chain makes the code dependent on the relationships between many potentially unrelated objects. [F 82]

- **`[F 181]` Hide Delegate _(Moving Features Between Objects)_**
- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 167]` Move Method _(Moving Features Between Objects)_**

***

## Metaprogramming Madness
_Ruby specific code smell_

> When Ruby's dynamic nature is misused, and metaprogramming resulting in obfuscated code. For example, `method_missing` can result in code that is difficult to understand. [F 86]

- **`[F 158]` Replace Dynamic Receptor with Dynamic Method Definition _(Composing Methods)_**
- **`[F 102]` Extract Method _(Composing Methods)_**
- **`[F 160]` Isolate Dynamic Receptor _(Composing Methods)_**

***

## Middle Man
_Inter-Class Smells_

> Delegation is good, and one of the key fundamental features of objects. But too much of a good thing can lead to objects that add no value, simply passing messages on to another object. [F 83]

- **`[F 185]` Remove Middle Man _(Moving Features Between Objects)_**
- **`[F 108]` Inline Method _(Composing Methods)_**
- **`[F 389]` Replace Delegation with Inheritance _(Dealing with Generalization)_**

***

## Oddball Solution
_Big Smells_

> When a problem is solved one way throughout a system and the same problem is solved another way in the same system, one of the solutions is the oddball or inconsistent solution. The presence of this smell usually indicates subtly duplicated code. [K 45]

- `[K 247]` Unify Interfaces with Adapter _(Big Refactorings)_

***

## Parallel Inheritance Hierarchies
_Inter-Class Smells_

> This is really a special case of Shotgun Surgery – every time you make a subclass of one class, you have to make a subclass of another. [F 81]

- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- **`[F 172]` Move Field _(Moving Features Between Objects)_**

***

## Primitive Obsession
_Inter-Class Smells_

> Primitives, which include integers, Strings, doubles, arrays and other low-level language elements, are generic because many people use them. Classes, on the other hand, may be as specific as you need them to be, since you create them for specific purposes. In many cases, classes provide a simpler and more natural way to model things than primitives. In addition, once you create a class, you’ll often discover how other code in a system belongs in that class. Fowler and Beck explain how primitive obsession manifests itself when code relies too much on primitives. This typically occurs when you haven’t yet seen how a higher-level abstraction can clarify or simplify your code. [F 79, K 41]

- **`[F 191]` Replace Data Value with Object _(Organizing Data)_**
- `[K 96]` Encapsulate Composite with Builder _(Big Refactorings)_
- **`[F 320]` Introduce Parameter Object _(Making Method Calls Simpler)_**
- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- `[K 144]` Move Embellishment to Decorator _(Big Refactorings)_
- `[K 129]` Replace Conditional Logic with Strategy _(Big Refactorings)_
- `[K 269]` Replace Implicit Language with Interpreter _(Big Refactorings)_
- `[K 178]` Replace Implicit Tree with Composite _(Big Refactorings)_
- `[K 166]` Replace State-Altering Conditionals with State _(Big Refactorings)_
- `[F 225, K 286]` Replace Type Code with Class _(Organizing Data)_
- **`[F 225]` Replace Type Code with Polymorphism _(Organizing Data)_**
- **`[F 239]` Replace Type Code with State/Strategy _(Organizing Data)_**
- **`[F 232]` Replace Type Code with Module Extension _(Organizing Data)_**
<!--- `[F 223]` Replace Type Code with Subclasses _(Organizing Data)_ -->
- **`[F 201]` Replace Array With Object _(Organizing Data)_**

***

## Refused Bequest
_Inter-Class Smells_

> This smell results from inheriting code you don't want. Instead of tolerating the inheritance, you write code to refuse the "bequest" -- which leads to ugly, confusing code, to say the least. [F 84]

<!-- - `[F 329]` Push Down Field _(Dealing with Generalization)_ -->
- **`[F 356]` Push Down Method _(Dealing with Generalization)_**
- **`[F 386]` Replace Inheritance with Delegation _(Dealing with Generalization)_**

***

## Repetitive boilerplate
_Ruby specific code smell_

> When class have the same unnecessary commonplace setup at the top of a file. [F 86]

- `[F 102]` Extract Method _(Composing Methods)_
- `[F 139]` Introduce Class Annotation _(Composing Methods)_

***

## Shotgun Surgery
_Inter-Class Smells_

> This smell is evident when you must change lots of pieces of code in different places simply to add a new or extended piece of behavior. [F 78]

- **`[F 167]` Move Method _(Moving Features Between Objects)_**
- **`[F 172]` Move Field _(Moving Features Between Objects)_**
- **`[F 179]` Inline Class _(Moving Features Between Objects)_**

***

## Solution Sprawl
_Big Smells_

> When code and/or data used in performing a responsibility becomes sprawled across numerous classes, solution sprawl is in the air. This smell often results from quickly adding a feature to a system without spending enough time simplifying and consolidating the design to best accommodate the feature. [K 43]

- `[K 68]` Move Creation Knowledge to Factory _(Big Refactorings)_

***

## Speculative Generality
_Class Smells_

> This odor exists when you have generic or abstract code that isn’t actually needed today. Such code often exists to support future behavior, which may or may not be necessary in the future. [F 81]

- **`[F 371]` Collapse Hierarchy _(Dealing with Generalization)_**
- **`[F 298]` Rename Method _(Making Method Calls Simpler)_**
- **`[F 302]` Remove Parameter _(Making Method Calls Simpler)_**
- **`[F 179]` Inline Class _(Moving Features Between Objects)_**

***

## Temporary Field

> Objects sometimes contain fields that don't seem to be needed all the time. The rest of the time, the field is empty or contains irrelevant data, which is difficult to understand. This is often an alternative to Long Parameter List. [F 82]

- **`[F 175]` Extract Class _(Moving Features Between Objects)_**
- **`[F 284, K 301]` Introduce Null Object _(Simplifying Conditional Expressions)_**

***

## Type Embedded In Name
_Name Smells_

> Including [Hungarian notation](https://en.wikipedia.org/wiki/Hungarian_notation).

- `[F 298]` Rename Method _(Making Method Calls Simpler)_
- Rename Field
- Rename Class

***

## Uncommunicative Name
_Name Smells_

- `[F 298]` Rename Method _(Making Method Calls Simpler)_
- Rename Field
- Rename Class

***

