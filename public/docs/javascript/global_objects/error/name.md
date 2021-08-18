Error.prototype.name
====================

The `name` property represents a name for the type of error. The initial value is "Error".

Description
-----------

By default, [`Error`](../error) instances are given the name "Error". The `name` property, in addition to the [`message`](message) property, is used by the [`Error.prototype.toString()`](tostring) method to create a string representation of the error.

Examples
--------

### Throwing a custom error

    var e = new Error('Malformed input'); // e.name is 'Error'

    e.name = 'ParseError';
    throw e;
    // e.toString() would return 'ParseError: Malformed input'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-error.prototype.name">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-error.prototype.name</span></a></td></tr></tbody></table>

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

`name`

1

12

1

6

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

-   [`Error.prototype.message`](message)
-   [`Error.prototype.toString()`](tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/name</a>
