async function expression
=========================

The `async function` keyword can be used to define `async` functions inside expressions.

You can also define async functions using an [async function statement](../statements/async_function).

Syntax
------

    async function [name]([param1[, param2[, ..., paramN]]]) {
       statements
    }

As of ES2015, you can also use [arrow functions](../functions/arrow_functions).

### Parameters

`name`  
The function name. Can be omitted, in which case the function is *anonymous*. The name is only local to the function body.

`paramN`  
The name of an argument to be passed to the function.

`statements`  
The statements which comprise the body of the function.

Description
-----------

An `async function` expression is very similar to, and has almost the same syntax as, an [`async function statement`](../statements/async_function). The main difference between an async `function` expression and an async `function` statement is the *function name*, which can be omitted in `async function` expressions to create *anonymous* functions. An `async function` expression can be used as an [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) (Immediately Invoked Function Expression) which runs as soon as it is defined. See also the chapter about [functions](../functions) for more information.

Examples
--------

### Simple example

    function resolveAfter2Seconds(x) {
      return new Promise(resolve => {
        setTimeout(() => {
          resolve(x);
        }, 2000);
      });
    };

    const add = async function(x) { // async function expression assigned to a variable
      let a = await resolveAfter2Seconds(20);
      let b = await resolveAfter2Seconds(30);
      return x + a + b;
    };

    add(10).then(v => {
      console.log(v);  // prints 60 after 4 seconds.
    });

    (async function(x) { // async function expression used as an IIFE
      let p_a = resolveAfter2Seconds(20);
      let p_b = resolveAfter2Seconds(30);
      return x + await p_a + await p_b;
    })(10).then(v => {
      console.log(v);  // prints 60 after 2 seconds.
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-async-function-definitions">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-async-function-definitions</span></a></td></tr></tbody></table>

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

`async_function`

55

15

52

No

42

10.1

55

55

52

42

10.3

6.0

See also
--------

-   [`async function`](../statements/async_function)
-   [`AsyncFunction`](../global_objects/asyncfunction) object
-   [`await`](await)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function</a>
