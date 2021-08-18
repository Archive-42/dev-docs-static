Array.prototype\[@@unscopables\]
================================

The `@@unscopable` symbol property contains property names that were not included in the ECMAScript standard prior to the ES2015 version. These properties are excluded from `with` statement bindings.

Description
-----------

The default array properties that are excluded from `with` bindings are:

-   [`at()`](at)
-   [`copyWithin()`](copywithin)
-   [`entries()`](entries)
-   [`fill()`](fill)
-   [`find()`](find)
-   [`findIndex()`](findindex)
-   [`includes()`](includes)
-   [`keys()`](keys)
-   [`values()`](values)

See [`Symbol.unscopables`](../symbol/unscopables) for how to set `unscopables` for your own objects.

Property attributes of `Array.prototype[@@unscopables]`

Writable

no

Enumerable

no

Configurable

yes

Examples
--------

### Use in with environments

The following code works fine in ES5 and below. However, in ECMAScript 2015 and later, the [`Array.prototype.keys()`](keys) method was introduced. That means that inside `with` environments, "keys" would now be the method and not the variable. This is where now the built-in `@@unscopables` `Array.prototype[@@unscopables]` symbol property comes into play and prevents that some of the Array methods are being scoped into the `with` statement.

    var keys = [];

    with (Array.prototype) {
      keys.push('something');
    }

    Object.keys(Array.prototype[Symbol.unscopables]);
    // ["at", "copyWithin", "entries", "fill", "find", "findIndex",
    //  "includes", "keys", "values"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype-@@unscopables">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype-@@unscopables</span></a></td></tr></tbody></table>

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

`@@unscopables`

38

12

48

No

25

10

38

38

48

25

10

3.0

See also
--------

-   [`Symbol.unscopables`](../symbol/unscopables)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@unscopables" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@unscopables</a>
