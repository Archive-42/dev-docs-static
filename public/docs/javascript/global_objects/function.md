Function
========

Every JavaScript function is actually a `Function` object. This can be seen with the code `(function(){}).constructor === Function`, which returns true.

Constructor
-----------

[`Function()`](function/function)  
Creates a new `Function` object. Calling the constructor directly can create functions dynamically but suffers from security and similar (but far less significant) performance issues to [`Global_Objects/eval`](eval). However, unlike eval, the `Function` constructor creates functions that execute in the global scope only.

Instance properties
-------------------

[`Function.prototype.arguments`](function/arguments)  
An array corresponding to the arguments passed to a function.  
This is deprecated as a property of [`Function`](function). Use the [`arguments`](../functions/arguments) object (available within the function) instead.

[`Function.prototype.caller`](function/caller)  
Specifies the function that invoked the currently executing function.  
This property is deprecated, and is only functional for some non-strict functions.

[`Function.prototype.displayName`](function/displayname)  
The display name of the function.

[`Function.prototype.length`](function/length)  
Specifies the number of arguments expected by the function.

[`Function.prototype.name`](function/name)  
The name of the function.

Instance methods
----------------

[`Function.prototype.apply(thisArg [, argsArray])`](function/apply)  
Calls a function and sets its `this` to the provided `thisArg`. Arguments can be passed as an [`Array`](array) object.

[`Function.prototype.bind(thisArg[, arg1[, arg2[, ...argN]]])`](function/bind)  
Creates a new function which, when called, has its `this` set to the provided `thisArg`. Optionally, a given sequence of arguments will be prepended to arguments provided the newly-bound function is called.

[`Function.prototype.call(thisArg[, arg1, arg2, ...argN])`](function/call)  
Calls a function and sets its `this` to the provided value. Arguments can be passed as they are.

[`Function.prototype.toString()`](function/tostring)  
Returns a string representing the source code of the function.  
Overrides the [`Object.prototype.toString`](object/tostring) method.

Examples
--------

### Difference between Function constructor and function declaration

Functions created with the `Function` constructor do not create closures to their creation contexts; they always are created in the global scope. When running them, they will only be able to access their own local variables and global ones, not the ones from the scope in which the `Function` constructor was created. This is different from using [`Global_Objects/eval`](eval) with code for a function expression.

    var x = 10;

    function createFunction1() {
        var x = 20;
        return new Function('return x;'); // this |x| refers global |x|
    }

    function createFunction2() {
        var x = 20;
        function f() {
            return x; // this |x| refers local |x| above
        }
        return f;
    }

    var f1 = createFunction1();
    console.log(f1());          // 10
    var f2 = createFunction2();
    console.log(f2());          // 20

While this code works in web browsers, `f1()` will produce a `ReferenceError` in Node.js, as `x` will not be found. This is because the top-level scope in Node is not the global scope, and `x` will be local to the module.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-function-objects">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-function-objects</span></a></td></tr></tbody></table>

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

`Function`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`Function`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`apply`

1

12

1

5.5

4

1

1

18

4

10.1

1

1.0

`arguments`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`bind`

7

12

4

9

11.6

5.1

4

18

4

12

6

1.0

`call`

1

12

1

5.5

4

1

1

18

4

10.1

1

1.0

`caller`

1

12

1

8

9.6

3

1

18

4

10.1

1

1.0

`displayName`

No

No

13

No

No

No

No

No

14

No

No

No

`length`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`name`

15

14

1

No

10.5

6

1

18

4

11

6

1.0

`toSource`

No

No

1-74

Starting in Firefox 74, `toSource()` is no longer available for use by web content. It is still allowed for internal and privileged code.

No

No

No

No

No

4

No

No

No

`toString`

1

12

1

5

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [Functions and function scope](../functions)
-   [`function`](../statements/function) statement
-   [`function`](../operators/function) expression
-   [`function*`](../statements/function*) statement
-   [`function*`](../operators/function*) expression
-   [`AsyncFunction`](asyncfunction)
-   [`GeneratorFunction`](generatorfunction)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function</a>
