Intl.RelativeTimeFormat.prototype.format()
==========================================

The `Intl.RelativeTimeFormat.prototype.format()` method formats a `value` and `unit` according to the locale and formatting options of this [`Intl.RelativeTimeFormat`](../relativetimeformat) object.

Syntax
------

    format(value, unit)

### Parameters

`value`  
Numeric value to use in the internationalized relative time message.

`unit`  
Unit to use in the relative time internationalized message. Possible values are: "`year`", "`quarter`", "`month`", "`week`", "`day`", "`hour`", "`minute`", "`second`". Plural forms are also permitted.

Description
-----------

The function returned by the `format` getter formats a value and a unit into a string according to the locale and formatting options of this [`Intl.RelativeTimeFormat`](../relativetimeformat) object.

Examples
--------

### Basic format usage

The following example shows how to create a relative time formatter using the English language.

    // Create a relative time formatter in your locale
    // with default values explicitly passed in.
    const rtf = new Intl.RelativeTimeFormat("en", {
        localeMatcher: "best fit", // other values: "lookup"
        numeric: "always", // other values: "auto"
        style: "long", // other values: "short" or "narrow"
    });

    // Format relative time using negative value (-1).
    rtf.format(-1, "day");
    // > "1 day ago"

    // Format relative time using positive  value (1).
    rtf.format(1, "day");
    // > "in 1 day"

### Using the auto option

If `numeric:auto` option is passed, it will produce the string `yesterday` or `tomorrow` instead of `1 day ago` or `in 1 day`. This allows to not always have to use numeric values in the output.

    // Create a relative time formatter in your locale
    // with numeric: "auto" option value passed in.
    const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

    // Format relative time using negative value (-1).
    rtf.format(-1, "day");
    // > "yesterday"

    // Format relative time using positive day unit (1).
    rtf.format(1, "day");
    // > "tomorrow"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.RelativeTimeFormat.prototype.format">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.RelativeTimeFormat.prototype.format</span></a></td></tr></tbody></table>

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

`format`

71

79

65

No

58

14

71

71

65

50

14

10.0

See also
--------

-   [`Intl.RelativeTimeFormat`](../relativetimeformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/format" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/format</a>
