Number.parseInt()
=================

The `Number.parseInt()` method parses a string argument and returns an integer of the specified radix or base.

Syntax
------

    Number.parseInt(string)
    Number.parseInt(string, radix)

### Parameters

`string`  
The value to parse. If this argument is not a string, then it is converted to one using the `ToString` abstract operation. Leading whitespace in this argument is ignored.

 `radix` <span class="badge inline optional">Optional</span>   
An integer between `2` and `36` that represents the *radix* (the base in mathematical numeral systems) of the `string`.

If `radix` is undefined or `0`, it is assumed to be `10` except when the number begins with the code unit pairs `0x` or `0X`, in which case a radix of `16` is assumed.

### Return value

An integer parsed from the given `string`.

If the `radix` is smaller than `2` or bigger than `36`, and the first non-whitespace character cannot be converted to a number, [`NaN`](../nan) is returned.

Polyfill
--------

    if (Number.parseInt === undefined) {
        Number.parseInt = window.parseInt
    }

Examples
--------

### Number.parseInt vs parseInt

This method has the same functionality as the global [`parseInt()`](../parseint) function:

    Number.parseInt === parseInt // true

and is part of ECMAScript 2015 (its purpose is modularization of globals). Please see [`parseInt()`](../parseint) for more detail and examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.parseint">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'Number.parseInt' in that specification.</span></a></td></tr></tbody></table>

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

`parseInt`

34

12

25

No

21

9

≤37

34

25

21

9

2.0

See also
--------

-   The [`Number`](../number) object it belongs to.
-   The global [`parseInt()`](../parseint) method.

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt</a>
