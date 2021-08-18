Intl.PluralRules.prototype.resolvedOptions()
============================================

The `Intl.PluralRules.prototype.resolvedOptions()` method returns a new object with properties reflecting the locale and plural formatting options computed during initialization of this [`Intl/PluralRules`](../pluralrules) object.

Syntax
------

    resolvedOptions()

### Return value

A new object with properties reflecting the locale and plural formatting options computed during the initialization of the given [`Intl/PluralRules`](../pluralrules) object.

Description
-----------

The resulting object has the following properties:

`locale`  
The BCP 47 language tag for the locale actually used. If any Unicode extension values were requested in the input BCP 47 language tag that led to this locale, the key-value pairs that were requested and are supported for this locale are included in `locale`.

`pluralCategories`  
An [`Array`](../../array) of plural categories used by the given locale, seleced from the list "`zero`", "`one`", "`two`", "`few`", "`many`" and "`other`".

`type`  
The type used (`cardinal` or `ordinal`).

Only one of the following two groups of properties is included:

`minimumIntegerDigits`  
`minimumFractionDigits`  
`maximumFractionDigits`  
The values provided for these properties in the `options` argument or filled in as defaults. These properties are present only if neither `minimumSignificantDigits` nor `maximumSignificantDigits` was provided in the `options` argument.

`minimumSignificantDigits`  
`maximumSignificantDigits`  
The values provided for these properties in the `options` argument or filled in as defaults. These properties are present only if at least one of them was provided in the `options` argument.

Examples
--------

### Using the `resolvedOptions` method

    var de = new Intl.PluralRules('de-DE');
    var usedOptions = de.resolvedOptions();

    usedOptions.locale;                // "de-DE"
    usedOptions.maximumFractionDigits; // 3
    usedOptions.minimumFractionDigits; // 0
    usedOptions.minimumIntegerDigits;  // 1
    usedOptions.pluralCategories;      // Array [ "one", "other" ]
    usedOptions.type;                  // "cardinal"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.pluralrules.prototype.resolvedoptions">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.pluralrules.prototype.resolvedoptions</span></a></td></tr></tbody></table>

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

63

18

58

No

50

13

63

63

58

46

13

8.0

See also
--------

-   [`Intl.PluralRules`](../pluralrules)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/resolvedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/resolvedOptions</a>
