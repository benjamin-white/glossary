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

**_Polyfill, Shim & Mixins &mdash;_**
While the three terms have different specific meanings and contexts they describe the same principle of adding additional functionality we desire, but that was not available. Polyfills and shims are about adding functionality to the environment (frequently the browser) while mixins relate to shareing methods within the code (where the functionality can be included rather than needing to be inherited from a class).


# Ruby Shorthand

    .reduce(:o) || .inject(:o) # Where 'o' is an arithmetic operation to be applied on a list or array of items.
    
    items.sort_by(&:length) # When a method requires no arguments this shorthand can be used.
    
    [*1..10] # Will expand to [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    
    condition ? true : false # One line ternary operator.
    
    method parameter=default # Sets default value for argument if none supplied.
    
    method value_one, *value_two # The splat allows zero or more arguments to be supplied.
                                   It will arrive inside the function as an array.
                                   
    %w'one two three' # Split string on whitespace, equivalent to 'one two three'.split(' ')
    
    %(string (syntax) with "custom" delimeters) # Custom delimeters can limit the need to backslash escape.
    
    one, two, three = %w'1 2 3' # Example of parallel assignment.
    
    a ||= b # Set a to b only if a is nil / undefined / false
    
