Boolean.prototype.toString()
============================

The `toString()` method returns a string representing the specified Boolean object.

Syntax
------

    toString()

### Return value

A string representing the specified [`Boolean`](../boolean) object.

Description
-----------

The [`Boolean`](../boolean) object overrides the `toString` method of the [`Object`](../object) object; it does not inherit [`Object.prototype.toString()`](../object/tostring). For `Boolean` objects, the `toString` method returns a string representation of the object.

JavaScript calls the `toString()` method automatically when a [`Boolean`](../boolean) is to be represented as a text value or when a [`Boolean`](../boolean) is referred to in a string concatenation.

For [`Boolean`](../boolean) objects and values, the built-in `toString()` method returns the string "`true`" or "`false`" depending on the value of the boolean object.

Examples
--------

### Using `toString()`

In the following code, `flag.toString()` returns "`true`":

    var flag = new Boolean(true);
    var myVar = flag.toString();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-boolean.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-boolean.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

1

12

1

3

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

-   [`Object.prototype.toString()`](../object/tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/toString</a>
