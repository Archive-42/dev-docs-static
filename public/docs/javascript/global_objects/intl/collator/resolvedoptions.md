Intl.Collator.prototype.resolvedOptions()
=========================================

The `Intl.Collator.prototype.resolvedOptions()` method returns a new object with properties reflecting the locale and collation options computed during initialization of this [`Intl/Collator`](../collator) object.

Syntax
------

    resolvedOptions()

### Return value

A new object with properties reflecting the locale and collation options computed during the initialization of the given [`Intl/Collator`](../collator) object.

Description
-----------

The resulting object has the following properties:

`locale`  
The BCP 47 language tag for the locale actually used. If any Unicode extension values were requested in the input BCP 47 language tag that led to this locale, the key-value pairs that were requested and are supported for this locale are included in `locale`.

`usage`  
`sensitivity`  
`ignorePunctuation`  
The values provided for these properties in the `options` argument or filled in as defaults.

`collation`  
The value requested using the Unicode extension key "`co`", if it is supported for `locale`, or "`default`".

`numeric`  
`caseFirst`  
The values requested for these properties in the `options` argument or using the Unicode extension keys "`kn`" and "`kf`" or filled in as defaults. If the implementation does not support these properties, they are omitted.

Examples
--------

### Using the resolvedOptions method

    var de = new Intl.Collator('de', { sensitivity: 'base' })
    var usedOptions = de.resolvedOptions();

    usedOptions.locale;            // "de"
    usedOptions.usage;             // "sort"
    usedOptions.sensitivity;       // "base"
    usedOptions.ignorePunctuation; // false
    usedOptions.collation;         // "default"
    usedOptions.numeric;           // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.collator.prototype.resolvedoptions">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.collator.prototype.resolvedoptions</span></a></td></tr></tbody></table>

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

24

12

29

11

15

10

4.4

25

56

14

10

1.5

See also
--------

-   [`Intl.Collator`](../collator)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/resolvedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/resolvedOptions</a>
