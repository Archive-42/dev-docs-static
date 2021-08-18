Intl.DisplayNames.prototype.resolvedOptions()
=============================================

The `Intl.DisplayNames.prototype.resolvedOptions()` method returns a new object with properties reflecting the locale and style formatting options computed during the construction of the current [`Intl/DisplayNames`](../displaynames) object.

Syntax
------

    resolvedOptions()

### Return value

An object with properties reflecting the locale and formatting options computed during the construction of the given [`Intl/DisplayNames`](../displaynames) object.

Description
-----------

The object returned by `resolvedOptions()` has the following properties:

`locale`  
The BCP 47 language tag for the locale actually used. If any Unicode extension values were requested in the input BCP 47 language tag that led to this locale, the key-value pairs that were requested and are supported for this locale are included in `locale`.

`style`  
The value provided for this property in the `options` argument of the constructor or the default value ("`long`"). Its value is either "`long`", "`short`", or "`narrow`".

`type`  
The value provided for this property in the `options` argument of the constructor or the default value ("`language`"). Its value is either "`language`", "`region`", "`script`", or "`currency`".

`fallback`  
The value provided for this property in the options argument of the constructor or the default value ("`code`"). Its value is either "`code`" or "`none`".

Examples
--------

### Using resolvedOptions

    const displayNames = new Intl.DisplayNames(['de-DE'], {type: 'region'});

    const usedOptions = displayNames.resolvedOptions();
    console.log(usedOptions.locale);   // "de-DE"
    console.log(usedOptions.style);    // "long"
    console.log(usedOptions.type);     // "region"
    console.log(usedOptions.fallback); // "code"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-Intl.DisplayNames.prototype.resolvedOptions">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-Intl.DisplayNames.prototype.resolvedOptions</span></a></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/resolvedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/resolvedOptions</a>
