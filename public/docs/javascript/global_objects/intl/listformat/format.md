Intl.ListFormat.prototype.format()
==================================

The `format()` method returns a string with a language-specific representation of the list.

Syntax
------

    format()
    format(list)

### Parameters

`list`  
An iterable object, such as an Array.

### Return value

A language-specific formatted string representing the elements of the list

Description
-----------

The `format()` method returns a string that has been formatted based on parameters provided in the `Intl.ListFormat` object. The `locales` and `options` parameters customize the behavior of `format()` and let applications specify the language conventions that should be used to format the list.

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

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.ListFormat.prototype.format">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.ListFormat.prototype.format</span></a></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/format" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/format</a>
