Date.prototype.toString()
=========================

The `toString()` method returns a string representing the specified [`Date`](../date) object.

Syntax
------

    toString()

### Return value

A string representing the given date.

Description
-----------

[`Date`](../date) instances inherit their `toString()` method from [`Date.prototype`](../date), not [`Object.prototype`](../object). `Date.prototype.toString()` returns a string representation of the Date in the format specified in ECMA-262 which can be summarised as:

-   Week day: 3 letter English week day name, e.g. "Sat"
-   space
-   Month name: 3 letter English month name, e.g. "Sep"
-   space
-   Date: 2 digit day in month, e.g. "01"
-   space
-   Year: 4 digit year, e.g. "2018"
-   space
-   Hour: 2 digit hour of day, e.g. "14"
-   colon
-   Minute: 2 digit minute of hour, e.g. "53"
-   colon
-   Second: 2 digit second of minute, e.g. "26"
-   space
-   The string "GMT"
-   Timezone offset sign, either:
    -   "+" for positive offsets (0 or greater)
    -   "-" for negative offsets (less than zero)
-   Two digit hour offset, e.g. "14"
-   Two digit minute offset, e.g. "00"
-   Optionally, a timezone name consisting of:
    -   space
    -   Left bracket, i.e. "("
    -   An implementation dependent string representation of the timezone, which might be an abbreviation or full name (there is no standard for names or abbreviations of timezones), e.g. "Line Islands Time" or "LINT"
    -   Right bracket, i.e. ")"

E.g. "Sat Sep 01 2018 14:53:26 GMT+1400 (LINT)"

Until ECMAScript 2018 (edition 9), the format of the string returned by `Date.prototype.toString` was implementation dependent. Therefore it should not be relied upon to be in the specified format.

The `toString()` method is automatically called when a date is to be represented as a text value, e.g. `console.log(new Date())`, or when a date is used in a string concatenation, such as `var today = 'Today is ' + new Date()`.

`toString()` is a generic method, it does not require that its `this` is a [`Date`](../date) instance. However, it must have an internal `[[TimeValue]]` property that can't be constructed using native javascript, so it's effectively limited to use with [`Date`](../date) instances. If called on a non–Date instance, a [`TypeError`](../typeerror) is thrown.

Examples
--------

### Using toString()

The following assigns the `toString()` value of a [`Date`](../date) object to `myVar`:

    var x = new Date();
    var myVar = x.toString(); // assigns a string value to myVar in the same format as:
                              // Mon Sep 08 1998 14:36:22 GMT-0700 (PDT)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-date.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-date.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [`Object.prototype.toString()`](../object/tostring)
-   [`Date.prototype.toDateString()`](todatestring)
-   [`Date.prototype.toLocaleString()`](tolocalestring)
-   [`Date.prototype.toTimeString()`](totimestring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toString</a>
