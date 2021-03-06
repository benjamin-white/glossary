# Glossary

## Modern programming can be quite confusing with an array of phrases that go beyond syntax and language specifics, here are a few of the more abstract concepts.

**_Duck Typing &mdash;_**
In essence, data types need not be declared in the code as they are inferred at runtime. If an object responds appropriately to the methods called on it, then everything is cool. This dynamic casting is in contrast to static languages such as Java & C.

**_Function Currying &mdash;_**<br>
This involves deferred execution (sort of like a promise) where a function can be passed all arguments to return the result, or arguments can be partially applied and a function is returned awaiting the remaining arguments. This promotes greater reuse and flexibility in function definitions. Currying is common in Haskell and Scala but can also be implemented using vanilla Javascript or with the use of a library (eg. http://ramdajs.com/0.21.0/index.html)

**_Tail Recursion &mdash;_**<br>
Recursion chews up a valuable and limited resource, the stack, and can lead to an unrecoverable type error: overflow. Tail Recursion however is a form of recursion that can avoid exceeding stack space during its execution. This means tail call optimization is slightly faster (no stack pushes or pops are required) and overflow exceptions are avoided.

**_Functional Programming &mdash;_**
Functional programming is an alternative paradigm to the imperative style. As such it seems daunting but also a powerful approach to understand, I need to try it out to get a feel for it!

**_Monkey Patching &mdash;_**
Modifying, extending or otherwise overwriting a language's core class or module. Generally not recomended due to the possibility of corrupting expected behaviour, whenever possible it is better to have a new class.

**_Encapsulation, Single Responsibility Principle & Closures &mdash;_**
Encapsulation refers to the wrapping of variables and methods together as a single unit and limiting the exposure of those variables to the larger world, kind of like a containment strategy! This can prevent unintended manipulation of data and hides complexity from interacting external Classes or methods. In some languages it can be specified using the 'private' keyword.<br>
SRP maintains that a function will ideally have one, clearly defined, responsibility. This makes code maintanence and debugging easier as it becomes harder to pollute a function's purpose when editing and easier to locate a problematic portion of code when things go wrong. In short it helps everyone a lot and makes life simpler, practice the technique and don't have long methods doing many different things!<br>
So I read a bit and trying to fully understand how Closures are implemented feels (I imagine) like getting lost in a huge forest, at night. Bearing that in mind a massivley simplified definition would be that a Closure binds together objects and / or values contingently. A function that uses variables outside itself or requires a return value from another function during execution will need to be bound to those and so together they all form a Closure, one practical effect is the values will not be garbage collected while still in use by the function.

**_Polyfill, Shim & Mixins &mdash;_**
While the three terms have different specific meanings and contexts they describe the same principle of adding additional functionality we desire, but that was not available. Polyfills and shims are about adding functionality to the environment (frequently the browser) while mixins relate to shareing methods within the code (where the functionality can be included rather than needing to be inherited from a class).

**_REPL, CRUD, REST &mdash;_**
* Read Evaluate Print Loop
* Create Read Update Delete
* Representational State Transfer

**_Test Doubles, Mocks & Stubs &mdash;_**
With these the nomenclature often overlaps seemingly as much based on the philopsophy of the person describing it as the particular testing framework being described. In what seems like the purest interpretation though tests can use stand in doubles to avoid the overhead, complexity and possible contamination of test results that comes with using a real object. Doubles is really an umbrella that covers the stratas Dummy, Fake, Mock & Stub. The first two of these act like placeholders, sometimes just being something to fill a gap in a parameter list; the later two are generally concerned with accepting messages, replying with predetermined responses and logging the behaviour of the subject under test. As such all doubles stand in for what would be a collaborator in the production environment. This then can bifuricate further into a distinction between testing state or behaviour (often messages), a distinction sometimes refered to as the 'Detroit' and 'London' styles of testing. The London style being closer to BDD. Martin Fowler has a good article explaining this in more detail (and clarity) http://martinfowler.com/articles/mocksArentStubs.html

**_TDD & BDD &mdash;_**
Test Driven Development was exposed by people like Kent Beck and the eXtreme Programming movement, advocating that the tests come before the code. Not only should the tests be written before code they should moreover inform the code being written following short R/G/R cycles. Here only enough code is written to make the tests pass then it is refactored. The technique can (counter intuitively at times) speed up production cycles and miminise long-term technical debt, though it is not without criticism such as when mocking is used excessivley following the London style.<br>
Behaviour Driven Development takes a cue from TDD but shifts the emphasis onto _'scenarios'_ and _'specifications'_ rather than tests in the terminology. To keep the development user-centric BDD uses an outside in approach building on the structure of TDD using a _role-feature_ matrix of user stories (ie. As a..., I want..., So that...). This then more easily and readably allows screnarios (tests) to be written using a _given / when / then_ notation. BDD is more highly concerned with the sending and receiving of messages and the distribution of responsibilities among classes and so strongly advocates the mocking approach.

**_Unit Test, Feature Test & Acceptance Test &mdash;_**
When applied to software tests _Unit Testing_ generally relates to the individual and unique components of a suite, often just a Class or even individual functions and methods. This is where test doubles have validity to ensure the unit being tested is isolated and is uniquely the subject of each test.<br>
This contrasts to (though works in partnership with) _Feature Tests_, which are less concerned with the internal workings of the program and more concerned with how a user would interact with the application in the wild. This testing frequently utilises an automated browser to simulate user actions in conjunction with a testing framework such as _Capybara_ and a helper webdriver such as _Selenium_. As such feature tests could be seen as higher level than unit tests and being concerned with the successful flow of user interactions through a public software interface.<br>
An _Acceptance test_ is then used to determine if the applcation has met the business requirements set for it. These tests are not limited to, but focused around, concepts of usability, scalability, performance, documentation and confidentiality. They are concerned with the product as a whole and its fitness for purpose.

**_Dependancy Injection &mdash;_**
In Javascript there is a similar concept called _pure functions_, and these inherently must have _referential transparency_. The core tennant with a pure function is that it does not reach outside itself into a wider scope to work as this would make testing, debugging and reuse much harder; the function would often be dependant on some cryptic object that then takes detective work to find. To circumvent this (and make the references more transparent) dependencies are always passed as a parameter to the function. They are _injected_ when the function is called rather than living permanently inside the function body.

**_Dependancy Inversion Principle &mdash;_**
At the heart of _Dependency Inversion_ is the premise that high level modules should not depend on low level ones for their uitility. This arises as in some situations the two are tightly coupled and there are certain scenarios for which this coupling proves highly problematic. Dependency inversion instead suggests to avoid this coupling and allow the levels to inteface through an intermediary abstraction layer. As such it might be beneficial to think of the principle more as high level dependency negation through abstration helpers; it does not so much invert the direction as limit the acuteness at higher levels. As with many principles here while it can be highly beneficial it may still not be appropriate (or neccessary) for every implementation.

**_SOLID Principles &mdash;_**
* Single Responsibility Principle
* Open / Closed
* Liskov Substitution Principle
* Inversion Of Control
* Dependancy Inversion

**_Inheritance vs. Composition &mdash;_**

**_Constructor vs. Initialise &mdash;_**

**_Declarative/Functional, Imperative & Procedural styles &mdash;_**

**_Anti Patterns &mdash;_**
    
