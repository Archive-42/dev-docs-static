Intl.DateTimeFormat.prototype.resolvedOptions()
===============================================

The `Intl.DateTimeFormat.prototype.resolvedOptions()` method returns a new object with properties reflecting the locale and date and time formatting options computed during initialization of this [`Intl/DateTimeFormat`](../datetimeformat) object.

Syntax
------

    resolvedOptions()

### Return value

A new object with properties reflecting the locale and date and time formatting options computed during the initialization of the given [`Intl/DateTimeFormat`](../datetimeformat) object.

Description
-----------

The resulting object has the following properties:

`locale`  
The BCP 47 language tag for the locale actually used. If any Unicode extension values were requested in the input BCP 47 language tag that led to this locale, the key-value pairs that were requested and are supported for this locale are included in `locale`.

`calendar`  
E.g. "gregory"

`numberingSystem`  
The values requested using the Unicode extension keys `"ca"` and `"nu"` or filled in as default values.

`timeZone`  
The value provided for this property in the `options` argument; [`undefined`](../../undefined) (representing the runtime's default time zone) if none was provided. Warning: Applications should not rely on [`undefined`](../../undefined) being returned, as future versions may return a [`String`](../../string) value identifying the runtime’s default time zone instead.

`hour12`  
The value provided for this property in the `options` argument or filled in as a default.

`weekday`  
`era`  
`year`  
`month`  
`day`  
`hour`  
`minute`  
`second`  
`timeZoneName`  
The values resulting from format matching between the corresponding properties in the `options` argument and the available combinations and representations for date-time formatting in the selected locale. Some of these properties may not be present, indicating that the corresponding components will not be represented in formatted output.

Examples
--------

### Using the resolvedOptions method

    var germanFakeRegion = new Intl.DateTimeFormat('de-XX', { timeZone: 'UTC' });
    var usedOptions = germanFakeRegion.resolvedOptions();

    usedOptions.locale;          // "de"
    usedOptions.calendar;        // "gregory"
    usedOptions.numberingSystem; // "latn"
    usedOptions.timeZone;        // "UTC"
    usedOptions.month;           // "numeric"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.datetimeformat.prototype.resolvedoptions">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.datetimeformat.prototype.resolvedoptions</span></a></td></tr></tbody></table>

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

`computed_timezone`

35

14

53

No

30

10

≤37

35

56

22

10

3.0

See also
--------

-   [`Intl.DateTimeFormat`](../datetimeformat)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/resolvedOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/resolvedOptions</a>
