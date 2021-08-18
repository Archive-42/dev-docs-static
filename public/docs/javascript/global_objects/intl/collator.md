Intl.Collator
=============

The `Intl.Collator` object enables language-sensitive string comparison.

Constructor
-----------

[`Intl.Collator()`](collator/collator)  
Creates a new `Collator` object.

Static methods
--------------

[`Intl.Collator.supportedLocalesOf()`](collator/supportedlocalesof)  
Returns an array containing those of the provided locales that are supported without having to fall back to the runtime's default locale.

Instance methods
----------------

[`Intl.Collator.prototype.compare`](collator/compare)  
Getter function that compares two strings according to the sort order of this [`Intl.Collator`](collator) object.

[`Intl.Collator.prototype.resolvedOptions()`](collator/resolvedoptions)  
Returns a new object with properties reflecting the locale and collation options computed during initialization of the object.

Examples
--------

### Using Collator

The following example demonstrates the different potential results for a string occurring before, after, or at the same level as another:

    console.log(new Intl.Collator().compare('a', 'c')); // → a negative value
    console.log(new Intl.Collator().compare('c', 'a')); // → a positive value
    console.log(new Intl.Collator().compare('a', 'a')); // → 0

Note that the results shown in the code above can vary between browsers and browser versions. This is because the values are implementation-specific. That is, the specification requires only that the before and after values are negative and positive.

### Using locales

The results provided by [`Intl/Collator/compare`](collator/compare) vary between languages. In order to get the sort order of the language used in the user interface of your application, make sure to specify that language (and possibly some fallback languages) using the `locales` argument:

    // in German, ä sorts with a
    console.log(new Intl.Collator('de').compare('ä', 'z'));
    // → a negative value

    // in Swedish, ä sorts after z
    console.log(new Intl.Collator('sv').compare('ä', 'z'));
    // → a positive value

### Using options

The results provided by [`Intl/Collator/compare`](collator/compare) can be customized using the `options` argument:

    // in German, ä has a as the base letter
    console.log(new Intl.Collator('de', { sensitivity: 'base' }).compare('ä', 'a'));
    // → 0

    // in Swedish, ä and a are separate base letters
    console.log(new Intl.Collator('sv', { sensitivity: 'base' }).compare('ä', 'a'));
    // → a positive value

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#collator-objects">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#collator-objects</span></a></td></tr></tbody></table>

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

`Collator`

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

`Collator`

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

`compare`

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

`supportedLocalesOf`

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

-   [`Intl`](../intl)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator</a>
