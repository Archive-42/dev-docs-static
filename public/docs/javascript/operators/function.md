function\* expression
=====================

The `function*` keyword can be used to define a generator function inside an expression.

Syntax
------

    function* [name]([param1[, param2[, ..., paramN]]]) {
       statements
    }

### Parameters

 `name` <span class="badge inline optional">Optional</span>   
The function name. Can be omitted, in which case the function is *anonymous*. The name is only local to the function body.

 `paramN` <span class="badge inline optional">Optional</span>   
The name of an argument to be passed to the function. A function can have up to 255 arguments.

`statements`  
The statements which comprise the body of the function.

Description
-----------

A `function*` expression is very similar to and has almost the same syntax as a [function\* statement](../statements/function*). The main difference between a `function*` expression and a `function*` statement is the *function name*, which can be omitted in `function*` expressions to create *anonymous* generator functions. See also the chapter about [`functions`](../functions) for more information.

Examples
--------

### Using function\*

The following example defines an unnamed generator function and assigns it to `x`. The function yields the square of its argument:

    let x = function*(y) {
       yield y * y;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-generator-function-definitions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-generator-function-definitions</span></a></td></tr></tbody></table>

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

`function*`

49

12

26

No

36

10

49

49

26

36

10

5.0

`trailing_comma`

58

79

52

No

45

10

58

58

52

43

10

7.0

See also
--------

-   [`function*`](../statements/function*) statement
-   [`GeneratorFunction`](../global_objects/generatorfunction) object
-   [The Iterator protocol](../iteration_protocols)
-   [`yield`](yield)
-   [`yield*`](yield*)
-   [`Function`](../global_objects/function) object
-   [`function`](../statements/function) statement
-   [`function`](function) expression
-   [Functions and function scope](../functions)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function*" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function*</a>
