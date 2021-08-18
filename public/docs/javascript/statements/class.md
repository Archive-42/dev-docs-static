class
=====

The **class declaration** creates a new class with a given name using prototype-based inheritance.

You can also define a class using a [class expression](../operators/class). But unlike a class expression, a class declaration doesn't allow an existing class to be declared again and will throw a [`SyntaxError`](../global_objects/syntaxerror) if attempted.

Syntax
------

    class name [extends otherName] {
      // class body
    }

Description
-----------

The class body of a class declaration is executed in [strict mode](../strict_mode). The `constructor` method is optional.

Class declarations are not [hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) (unlike [function declarations](function)).

Examples
--------

### A simple class declaration

In the following example, we first define a class named `Polygon`, then extend it to create a class named `Square`.

Note that `super()`, used in the `constructor`, can only be used in constructors, and *must* be called *before* the `this` keyword can be used.

    class Polygon {
      constructor(height, width) {
        this.name = 'Polygon';
        this.height = height;
        this.width = width;
      }
    }

    class Square extends Polygon {
      constructor(length) {
        super(length, length);
        this.name = 'Square';
      }
    }

### Attempting to declare a class twice

Re-declaring a class using the class declaration throws a [`SyntaxError`](../global_objects/syntaxerror).

    class Foo {};
    class Foo {}; // Uncaught SyntaxError: Identifier 'Foo' has already been declared

The same error is thrown when a class has been defined before using the class expression.

    let Foo = class {};
    class Foo {}; // Uncaught SyntaxError: Identifier 'Foo' has already been declared

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-class-definitions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-class-definitions</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`class`

49

42-49

Strict mode is required.

42-49

13

45

No

36

29-36

Strict mode is required.

29-36

10.1

49

42-49

Strict mode is required.

49

42-49

Strict mode is required.

42-49

45

36

29-36

Strict mode is required.

29-36

10.3

5.0

4.0-5.0

Strict mode is required.

See also
--------

-   [`function` declaration](function)
-   [`class` expression](../operators/class)
-   [Classes](../classes)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class</a>
