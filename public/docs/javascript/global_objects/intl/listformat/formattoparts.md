Intl.ListFormat.prototype.formatToParts()
=========================================

The `Intl.ListFormat.prototype.formatToParts()` method returns an [`Array`](../../array) of objects representing the different components that can be used to format a list of values in a locale-aware fashion.

Syntax
------

    formatToParts(list)

### Parameters

`list`  
An [`Array`](../../array) of values to be formatted according to a locale.

### Return value

An [`Array`](../../array) of components which contains the formatted parts from the list.

Description
-----------

Whereas [`Intl.ListFormat.prototype.format()`](format) returns a string being the formatted version of the list (according to the given locale and style options), `formatToParts()` returns an array of the different components of the formatted string.

Each element of the resulting array has two properties: `type` and `value`. The `type` property may be either "`element`", which refers to a value from the list, or "`literal`" which refers to a linguistic construct. The `value` property gives the content, as a string, of the token.

The locale and style options used for formatting are given when constructing the [`Intl.ListFormat`](../listformat) instance.

Examples
--------

### Using formatToParts

    const fruits = ['Apple', 'Orange', 'Pineapple'];
    const myListFormat = new Intl.ListFormat('en-GB', { style: 'long', type: 'conjunction' });

    console.table(myListFormat.formatToParts(fruits));
    // [
    //  { "type": "element", "value": "Apple" },
    //  { "type": "literal", "value": ", " },
    //  { "type": "element", "value": "Orange" },
    //  { "type": "literal", "value": ", and " },
    //  { "type": "element", "value": "Pineapple" }
    // ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.ListFormat.prototype.formatToParts">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.ListFormat.prototype.formatToParts</span></a></td></tr></tbody></table>

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

`formatToParts`

72

79

78

No

60

14.1

72

72

79

51

14.5

No

See also
--------

-   [`Intl.ListFormat`](../listformat)
-   [`Intl.ListFormat.prototype.format()`](format)
-   [`Intl.RelativeTimeFormat.prototype.formatToParts()`](../relativetimeformat/formattoparts)
-   [`Intl.NumberFormat.prototype.formatToParts()`](../numberformat/formattoparts)
-   [`Intl.DateTimeFormat.prototype.formatToParts()`](../datetimeformat/formattoparts)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/formatToParts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/formatToParts</a>
