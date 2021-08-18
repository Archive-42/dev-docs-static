Intl.PluralRules
================

The `Intl.PluralRules` object enables plural-sensitive formatting and plural-related language rules.

Constructor
-----------

[`Intl.PluralRules()`](pluralrules/pluralrules)  
Creates a new `Intl.PluralRules` object.

Static methods
--------------

[`Intl.PluralRules.supportedLocalesOf()`](pluralrules/supportedlocalesof)  
Returns an array containing those of the provided locales that are supported without having to fall back to the runtime's default locale.

Instance methods
----------------

[`Intl.PluralRules.prototype.resolvedOptions()`](pluralrules/resolvedoptions)  
Returns a new object with properties reflecting the locale and collation options computed during initialization of the object.

[`Intl.PluralRules.prototype.select()`](pluralrules/select)  
Returns a [`String`](../string) indicating which plural rule to use for locale-aware formatting.

Examples
--------

### Using locales

This example shows some of the variations in localized plural rules. In order to get the format of the language used in the user interface of your application, make sure to specify that language (and possibly some fallback languages) using the `locales` argument:

    // Arabic has different plural rules

    new Intl.PluralRules('ar-EG').select(0);
    // → 'zero'
    new Intl.PluralRules('ar-EG').select(1);
    // → 'one'
    new Intl.PluralRules('ar-EG').select(2);
    // → 'two'
    new Intl.PluralRules('ar-EG').select(6);
    // → 'few'
    new Intl.PluralRules('ar-EG').select(18);
    // → 'many'

Polyfill
--------

[formatjs Intl.PluralRules polyfill](https://formatjs.io/docs/polyfills/intl-pluralrules)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#pluralrules-objects">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#pluralrules-objects</span></a></td></tr></tbody></table>

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

`PluralRules`

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

`PluralRules`

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

`select`

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

`supportedLocalesOf`

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

-   [`Intl`](../intl)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules</a>
