Boolean.prototype.valueOf()
===========================

The `valueOf()` method returns the primitive value of a [`Boolean`](../boolean) object.

Syntax
------

    valueOf()

### Return value

The primitive value of the given [`Boolean`](../boolean) object

Description
-----------

The `valueOf()` method of [`Boolean`](../boolean) returns the primitive value of a `Boolean` object or literal `Boolean` as a Boolean data type.

This method is usually called internally by JavaScript and not explicitly in code.

Examples
--------

### Using `valueOf()`

    x = new Boolean();
    myVar = x.valueOf(); // assigns false to myVar

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-boolean.prototype.valueof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-boolean.prototype.valueof</span></a></td></tr></tbody></table>

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

-   [`Object.prototype.valueOf()`](../object/valueof)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/valueOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/valueOf</a>
