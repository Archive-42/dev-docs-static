Intl.RelativeTimeFormat.prototype.formatToParts()
=================================================

The `Intl.RelativeTimeFormat.prototype.formatToParts()` method returns an [`Array`](../../array) of objects representing the relative time format in parts that can be used for custom locale-aware formatting.

Syntax
------

    formatToParts(value, unit)

### Parameters

`value`  
Numeric value to use in the internationalized relative time message.

`unit`  
Unit to use in the relative time internationalized message. Possible values are: "`year`", "`quarter`", "`month`", "`week`", "`day`", "`hour`", "`minute`", "`second`". Plural forms are also permitted.

### Return value

An [`Array`](../../array) of objects containing the formatted relative time in parts.

Description
-----------

The `Intl.RelativeTimeFormat.prototype.formatToParts` method is a version of the format method which it returns an array of objects which represent "parts" of the object, separating the formatted number into its consituent parts and separating it from other surrounding text. These objects have two properties: type a `NumberFormat` formatToParts type, and value, which is the String which is the component of the output. If a "part" came from `NumberFormat`, it will have a unit property which indicates the unit being formatted; literals which are part of the larger frame will not have this property.

Examples
--------

### Using formatToParts

    const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

    // Format relative time using the day unit
    rtf.formatToParts(-1, "day");
    // > [{ type: "literal", value: "yesterday"}]

    rtf.formatToParts(100, "day");
    // > [{ type: "literal", value: "in " },
    // >  { type: "integer", value: "100", unit: "day" },
    // >  { type: "literal", value: " days" }]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.RelativeTimeFormat.prototype.formatToParts">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.RelativeTimeFormat.prototype.formatToParts</span></a></td></tr></tbody></table>

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

71

79

70

No

58

14

71

71

79

50

14

10.0

See also
--------

-   [`Intl.RelativeTimeFormat`](../relativetimeformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/formatToParts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/formatToParts</a>
