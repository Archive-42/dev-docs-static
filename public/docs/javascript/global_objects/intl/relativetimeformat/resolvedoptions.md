Intl.RelativeTimeFormat.prototype.resolvedOptions()
===================================================

The `Intl.RelativeTimeFormat.prototype.resolvedOptions()` method returns a new object with properties reflecting the locale and relative time formatting options computed during initialization of this [`Intl/RelativeTimeFormat`](../relativetimeformat) object.

Syntax
------

    resolvedOptions()

### Return value

A new object with properties reflecting the locale and number formatting options computed during the initialization of the given [`Intl/RelativeTimeFormat`](../relativetimeformat) object.

Description
-----------

The resulting object has the following properties:

`locale`  
The BCP 47 language tag for the locale actually used. If any Unicode extension values were requested in the input BCP 47 language tag that led to this locale, the key-value pairs that were requested and are supported for this locale are included in `locale`.

`style`  
The length of the internationalized message. Possible values are:

-   "`long`" (default, e.g., `in 1 month`)
-   "`short`" (e.g., `in 1 mo.`),
-   or "`narrow`" (e.g., `in 1 mo.`). The narrow style could be similar to the short style for some locales.

`numeric`  
The format of output message. Possible values are:

-   "`always`" (default, e.g., `1 day ago`),
-   or "`auto`" (e.g., `yesterday`). The "`auto`" value allows to not always have to use numeric values in the output.

`numberingSystem`  
The value requested using the Unicode extension key "`nu`" or filled in as a default.

Examples
--------

### Using the `resolvedOptions` method

    var de = new Intl.RelativeTimeFormat('de-DE');
    var usedOptions = de.resolvedOptions();

    usedOptions.locale;          // "de-DE"
    usedOptions.style;           // "long"
    usedOptions.numeric;         // "always"
    usedOptions.numberingSystem; // "latn"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.relativetimeformat.prototype.resolvedoptions">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.relativetimeformat.prototype.resolvedoptions</span></a></td></tr></tbody></table>

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

`resolvedOptions`

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

`numberingSystem`

73

79

70

No

60

14

73

73

79

52

14

No

See also
--------

-   [`Intl.RelativeTimeFormat`](../relativetimeformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/resolvedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/resolvedOptions</a>
