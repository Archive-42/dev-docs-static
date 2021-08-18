Date.prototype.valueOf()
========================

The `valueOf()` method returns the primitive value of a [`Date`](../date) object.

Syntax
------

    valueOf()

### Return value

The number of milliseconds between 1 January 1970 00:00:00 UTC and the given date.

Description
-----------

The `valueOf()` method returns the primitive value of a [`Date`](../date) object as a number data type, the number of milliseconds since midnight 01 January, 1970 UTC.

This method is functionally equivalent to the [`Date.prototype.getTime()`](gettime) method.

This method is usually called internally by JavaScript and not explicitly in code.

Examples
--------

### Using valueOf()

    var x = new Date(56, 6, 17);
    var myVar = x.valueOf();      // assigns -424713600000 to myVar

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-date.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-date.prototype.valueof</span></a></td></tr></tbody></table>

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

`valueOf`

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

See also
--------

-   [`Object.prototype.valueOf()`](../object/valueof)
-   [`Date.prototype.getTime()`](gettime)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/valueOf</a>
