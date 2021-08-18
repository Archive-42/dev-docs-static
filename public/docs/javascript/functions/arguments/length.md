arguments.length
================

The `arguments.length` property contains the number of arguments passed to the function.

Description
-----------

The arguments.length property provides the number of arguments actually passed to a function. This can be more or less than the defined parameter's count (see [`Function.length`](../../global_objects/function/length)).

Examples
--------

### Using `arguments.length`

In this example we define a function that can add two or more numbers together.

    function adder(base /*, n2, ... */) {
      base = Number(base);
      for (var i = 1; i < arguments.length; i++) {
        base += Number(arguments[i]);
      }
      return base;
    }

**Note:** Note the difference between [`Function.length`](../../global_objects/function/length) and arguments.length

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-arguments-exotic-objects">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-arguments-exotic-objects</span></a></td></tr></tbody></table>

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

`length`

1

12

1

4

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [`Function`](../../global_objects/function)
-   [`Function.length`](../../global_objects/function/length)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/length</a>
