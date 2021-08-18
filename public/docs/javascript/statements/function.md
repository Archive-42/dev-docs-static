function declaration
====================

The **function declaration** (function statement) defines a function with the specified parameters.

You can also define functions using the [`Function`](../global_objects/function) constructor and a [function expression](../operators/function).

Syntax
------

    function name([param[, param,[..., param]]]) {
       [statements]
    }

`name`  
The function name.

 `param` <span class="badge inline optional">Optional</span>   
The name of an argument to be passed to the function. Maximum number of arguments varies in different engines.

 `statements` <span class="badge inline optional">Optional</span>   
The statements which comprise the body of the function.

Description
-----------

A function created with a function declaration is a `Function` object and has all the properties, methods and behavior of `Function` objects. See [`Function`](../global_objects/function) for detailed information on functions.

A function can also be created using an expression (see [function expression](../operators/function)).

By default, functions return `undefined`. To return any other value, the function must have a [`return`](return) statement that specifies the value to return.

### Conditionally created functions

Functions can be conditionally declared, that is, a function statement can be nested within an `if` statement, however the results are inconsistent across implementations and therefore this pattern should not be used in production code. For conditional function creation, use function expressions instead.

    var hoisted = "foo" in this;
    console.log(`'foo' name ${hoisted ? "is" : "is not"} hoisted. typeof foo is ${typeof foo}`);
    if (false) {
      function foo(){ return 1; }
    }

    // In Chrome:
    // 'foo' name is hoisted. typeof foo is undefined
    //
    // In Firefox:
    // 'foo' name is hoisted. typeof foo is undefined
    //
    // In Edge:
    // 'foo' name is not hoisted. typeof foo is undefined
    //
    // In Safari:
    // 'foo' name is hoisted. typeof foo is function

The results are exactly the same for a condition that evaluates to true

    var hoisted = "foo" in this;
    console.log(`'foo' name ${hoisted ? "is" : "is not"} hoisted. typeof foo is ${typeof foo}`);
    if (true) {
      function foo(){ return 1; }
    }

    // In Chrome:
    // 'foo' name is hoisted. typeof foo is undefined
    //
    // In Firefox:
    // 'foo' name is hoisted. typeof foo is undefined
    //
    // In Edge:
    // 'foo' name is not hoisted. typeof foo is undefined
    //
    // In Safari:
    // 'foo' name is hoisted. typeof foo is function

### Function declaration hoisting

Function declarations in JavaScript are hoisted to the top of the enclosing function or global scope. You can use the function before you declared it:

    hoisted(); // logs "foo"

    function hoisted() {
      console.log('foo');
    }

Note that [function expressions](../operators/function) are not hoisted:

    notHoisted(); // TypeError: notHoisted is not a function

    var notHoisted = function() {
       console.log('bar');
    };

Examples
--------

### Using function

The following code declares a function that returns the total amount of sales, when given the number of units sold of products `a`, `b`, and `c`.

    function calc_sales(units_a, units_b, units_c) {
       return units_a * 79 + units_b * 129 + units_c * 699;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-function-definitions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-function-definitions</span></a></td></tr></tbody></table>

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

`function`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

`trailing_comma_in_parameters`

58

14

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

-   [`Function`](../global_objects/function)
-   [function expression](../operators/function)
-   [function\* statement](function*)
-   [function\* expression](../operators/function*)
-   [Arrow functions](../functions/arrow_functions)
-   [`GeneratorFunction`](../global_objects/generatorfunction)
-   [async function](async_function)
-   [async function expression](../operators/async_function)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function</a>
