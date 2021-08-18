Intl.ListFormat() constructor
=============================

The `Intl.ListFormat()` constructor creates [`Intl.ListFormat`](../listformat) objects that enable language-sensitive list formatting.

Syntax
------

    new Intl.ListFormat()
    new Intl.ListFormat(locales)
    new Intl.ListFormat(locales, options)

### Parameters

 `locales` <span class="badge inline optional">Optional</span>   
A string with a BCP 47 language tag, or an array of such strings. For the general form and interpretation of the `locales` argument, see the [Intl](../../intl#locale_identification_and_negotiation) page.

 `options` <span class="badge inline optional">Optional</span>   
An object with some or all of the following properties:

`localeMatcher`  
The locale matching algorithm to use. Possible values are "`lookup`" and "`best fit`"; the default is "`best fit`". For information about this option, see the [Intl](../../intl#locale_negotiation) page.

`type`  
The format of output message. Possible values are "`conjunction`" that stands for "and"-based lists (default, e.g., "`A, B, and C`"), or "`disjunction`" that stands for "or"-based lists (e.g., "`A, B, or C`"). "`unit`" stands for lists of values with units (e.g., "`5 pounds, 12 ounces`").

`style`  
The length of the formatted message. Possible values are: "`long`" (default, e.g., "`A, B, and C`"); "`short`" (e.g., "`A, B, C`"), or "`narrow`" (e.g., "`A B C`"). When `style` is "`short`" or "`narrow`", "`unit`" is the only allowed value for the type option.

Examples
--------

### Using format

The following example shows how to create a List formatter using the English language.

    const list = ['Motorcycle', 'Bus', 'Car'];

     console.log(new Intl.ListFormat('en-GB', { style: 'long', type: 'conjunction' }).format(list));
    // > Motorcycle, Bus and Car

     console.log(new Intl.ListFormat('en-GB', { style: 'short', type: 'disjunction' }).format(list));
    // > Motorcycle, Bus or Car

     console.log(new Intl.ListFormat('en-GB', { style: 'narrow', type: 'unit' }).format(list));
    // > Motorcycle Bus Car

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl-listformat-constructor">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl-listformat-constructor</span></a></td></tr></tbody></table>

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

`ListFormat`

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
-   [`Intl`](../../intl)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat</a>
