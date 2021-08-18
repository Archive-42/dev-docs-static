Number.NaN
==========

The `Number.NaN` property represents Not-A-Number. Equivalent of [`NaN`](../nan).

You do not have to create a [`Number`](../number) object to access this static property (use `Number.NaN`).

Property attributes of `Number.NaN`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Checking whether values are numeric

    function sanitise(x) {
      if (isNaN(x)) {
        return Number.NaN;
      }
      return x;
    }

### Testing against NaN

See [Testing against NaN](../nan#testing_against_nan) on the `NaN` page.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-number.nan">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-number.nan</span></a></td></tr></tbody></table>

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

`NaN`

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

-   The global [`NaN`](../nan) object.
-   The [`Number`](../number) object it belongs to.

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN</a>
