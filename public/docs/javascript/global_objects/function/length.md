Function.length
===============

The `length` property indicates the number of parameters expected by the function.

Property attributes of `Function.length`

Writable

no

Enumerable

no

Configurable

yes

Description
-----------

`length` is a property of a function object, and indicates how many arguments the function expects, i.e. the number of formal parameters. This number excludes the [rest parameter](../../functions/rest_parameters) and only includes parameters before the first one with a default value. By contrast, [`arguments.length`](../../functions/arguments/length) is local to a function and provides the number of arguments actually passed to the function.

### Data property of the Function constructor

The [`Function`](../function) constructor is itself a [`Function`](../function) object. Its `length` data property has a value of 1. The property attributes are: Writable: `false`, Enumerable: `false`, Configurable: `true`.

### Property of the Function prototype object

The length property of the [`Function`](../function) prototype object has a value of 0.

Examples
--------

### Using function length

    console.log(Function.length); /* 1 */

    console.log((function()        {}).length); /* 0 */
    console.log((function(a)       {}).length); /* 1 */
    console.log((function(a, b)    {}).length); /* 2 etc. */

    console.log((function(...args) {}).length);
    // 0, rest parameter is not counted

    console.log((function(a, b = 1, c) {}).length);
    // 1, only parameters before the first one with
    // a default value is counted

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-function-instances-length">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-function-instances-length</span></a></td></tr></tbody></table>

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

3

1

1

18

4

10.1

1

1.0

`configurable_true`

43

12

37

No

30

10

43

43

37

30

10

4.0

See also
--------

-   [`Function`](../function)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length</a>
