Date.prototype\[@@toPrimitive\]
===============================

The `[@@toPrimitive]()` method converts a `Date` object to a primitive value.

Syntax
------

    Date()[Symbol.toPrimitive](hint);

### Return value

The primitive value of the given [`Date`](../date) object. Depending on the argument, the method can return either a string or a number.

Description
-----------

The `[@@toPrimitive]()` method of the [`Date`](../date) object returns a primitive value, that is either of type number or of type string.

If `hint` is `string` or `default`, `[@@toPrimitive]()` tries to call the [`toString`](../object/tostring) method. If the `toString` property does not exist, it tries to call the [`valueOf`](../object/valueof) method and if the `valueOf` does not exist either, `[@@toPrimitive]()` throws a [`TypeError`](../typeerror).

If `hint` is `number`, `[@@toPrimitive]()` first tries to call `valueOf`, and if that fails, it calls `toString`.

JavaScript calls the `[@@toPrimitive]()` method to convert an object to a primitive value. You rarely need to invoke the `[@@toPrimitive]()` method yourself; JavaScript automatically invokes it when encountering an object where a primitive value is expected.

Examples
--------

### Returning date primitives

    const testDate = new Date(1590757517834);
    // "Date Fri May 29 2020 14:05:17 GMT+0100 (British Summer Time)"

    testDate[Symbol.toPrimitive]('string');
    // Returns "Date Fri May 29 2020 14:05:17 GMT+0100 (British Summer Time)"

    testDate[Symbol.toPrimitive]('number');
    // Returns "1590757517834"

    testDate[Symbol.toPrimitive]('default');
    // Returns "Date Fri May 29 2020 14:05:17 GMT+0100 (British Summer Time)"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-date.prototype-@@toprimitive">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-date.prototype-@@toprimitive</span></a></td></tr></tbody></table>

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

`@@toPrimitive`

47

15

44

No

34

10

47

47

44

34

10

5.0

See also
--------

-   [`Symbol.toPrimitive`](../symbol/toprimitive)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/@@toPrimitive" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/@@toPrimitive</a>
