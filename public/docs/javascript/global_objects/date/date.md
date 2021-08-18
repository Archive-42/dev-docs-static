Date() constructor
==================

Creates a JavaScript `Date` instance that represents a single moment in time in a platform-independent format.`Date` objects contain a `Number` that represents milliseconds since 1 January 1970 UTC.

Syntax
------

    new Date()
    new Date(value)
    new Date(dateString)

    new Date(year, monthIndex)
    new Date(year, monthIndex, day)
    new Date(year, monthIndex, day, hours)
    new Date(year, monthIndex, day, hours, minutes)
    new Date(year, monthIndex, day, hours, minutes, seconds)
    new Date(year, monthIndex, day, hours, minutes, seconds, milliseconds)

**Note:** The only correct way to instantiate a new `Date` object is by using the <span class="page-not-created">`new`</span> operator. If you call the `Date` object directly, such as `now = Date()`, the returned value is a string rather than a `Date` object.

### Parameters

There are four basic forms for the `Date()` constructor:

1.  #### No parameters

    When no parameters are provided, the newly-created `Date` object represents the current date and time as of the time of instantiation.

2.  #### Time value or timestamp number

    `value`  
    An integer value representing the number of milliseconds since January 1, 1970, 00:00:00 UTC (the ECMAScript epoch, equivalent to the UNIX epoch), with leap seconds ignored. Keep in mind that most [UNIX Timestamp](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap04.html#tag_04_16) functions are only accurate to the nearest second.

3.  #### Timestamp string

    `dateString`  
    A string value representing a date, specified in a format recognized by the [`Date.parse()`](parse) method. (These formats are [IETF-compliant RFC 2822 timestamps](https://datatracker.ietf.org/doc/html/rfc2822#page-14), and also strings in a [version of ISO8601](https://www.ecma-international.org/ecma-262/11.0/#sec-date.parse).)

    **Note:** Parsing of date strings with the `Date` constructor (and `Date.parse()`, which works the same way) is *strongly discouraged* due to browser differences and inconsistencies.

    -   Support for [RFC 2822](https://datatracker.ietf.org/doc/html/rfc2822) format strings is by convention only.
    -   Support for ISO 8601 formats differs in that date-only strings (e.g. `"1970-01-01"`) are treated as UTC, not local.

4.  #### Individual date and time component values

    Given at least a year and month, this form of `Date()` returns a `Date` object whose component values (year, month, day, hour, minute, second, and millisecond) all come from the following parameters. Any missing fields are given the lowest possible value (`1` for `day` and `0` for every other component). The parameter values are all evaluated against the local time zone, rather than UTC.

    `year`  
    Integer value representing the year.

    Values from `0` to `99` map to the years `1900` to `1999`. All other values are the actual year. See the [example](../date#two_digit_years_map_to_1900_%e2%80%93_1999).

    `monthIndex`  
    Integer value representing the month, beginning with `0` for January to `11` for December.

     `day` <span class="badge inline optional">Optional</span>   
    Integer value representing the day of the month. The default is `1`.

     `hours` <span class="badge inline optional">Optional</span>   
    Integer value representing the hour of the day. The default is `0` (midnight).

     `minutes` <span class="badge inline optional">Optional</span>   
    Integer value representing the minute segment of a time. The default is `0` minutes past the hour.

     `seconds` <span class="badge inline optional">Optional</span>   
    Integer value representing the second segment of a time. The default is `0` seconds past the minute.

     `milliseconds` <span class="badge inline optional">Optional</span>   
    Integer value representing the millisecond segment of a time. The default is `0` milliseconds past the second.

Examples
--------

### Several ways to create a Date object

The following examples show several ways to create JavaScript dates:

**Note:** Parsing of date strings with the `Date` constructor (and `Date.parse`, they are equivalent) is strongly discouraged due to browser differences and inconsistencies.

    let today = new Date()
    let birthday = new Date('December 17, 1995 03:24:00')
    let birthday = new Date('1995-12-17T03:24:00')
    let birthday = new Date(1995, 11, 17)            // the month is 0-indexed
    let birthday = new Date(1995, 11, 17, 3, 24, 0)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-date-constructor">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'Date' in that specification.</span></a></td></tr></tbody></table>

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

`Date`

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

-   [`Date`](../date)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date</a>
