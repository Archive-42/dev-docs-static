Intl.DisplayNames() constructor
===============================

The `Intl.DisplayNames()` constructor creates [`Intl.DisplayNames`](../displaynames) objects that enable the consistent translation of language, region and script display names.

Syntax
------

    new Intl.DisplayNames()
    new Intl.DisplayNames(locales)
    new Intl.DisplayNames(locales, options)

### Parameters

 `locales` <span class="badge inline optional">Optional</span>   
A string with a BCP 47 language tag, or an array of such strings. For the general form and interpretation of the `locales` argument, see the [Intl](../../intl#locale_identification_and_negotiation) page. The following Unicode extension key is allowed:

`nu`  
The numbering system to be used. Possible values include: "`arab`", "`arabext`", "`bali`", "`beng`", "`deva`", "`fullwide`", "`gujr`", "`guru`", "`hanidec`", "`khmr`", "`knda`", "`laoo`", "`latn`", "`limb`", "`mlym`", "`mong`", "`mymr`", "`orya`", "`tamldec`", "`telu`", "`thai`", "`tibt`".

 `options` <span class="badge inline optional">Optional</span>   
An object with some or all of the following properties:

`localeMatcher`  
The locale matching algorithm to use. Possible values are "`lookup`" and "`best fit`"; the default is "`best fit`". For information about this option, see the [Intl](../../intl#locale_negotiation) page.

`style`  
The formatting style to use, the default is "`long`".

-   "`narrow`"
-   "`short`"
-   "`long`"

`type`  
The type to use.

-   "`language`"
-   "`region`"
-   "`script`"
-   "`currency`"

`fallback`  
The fallback to use, the default is "`code`".

-   "`code`"
-   "`none`"

Examples
--------

### Basic usage

In basic use without specifying a locale, a formatted string in the default locale and with default options is returned.

    console.log((new Intl.DisplayNames([], {type: 'language'})).of('US'));
    // Expected output: 'us'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl-displaynames-constructor">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl-displaynames-constructor</span></a></td></tr></tbody></table>

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

`DisplayNames`

81

81

86

No

68

14.1

81

81

86

58

14.5

No

See also
--------

-   [`Intl.DisplayNames`](../displaynames)
-   [`Intl`](../../intl)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/DisplayNames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/DisplayNames</a>
