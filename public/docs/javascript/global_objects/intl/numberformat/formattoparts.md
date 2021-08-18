Intl.NumberFormat.prototype.formatToParts()
===========================================

The `Intl.Numberformat.prototype.formatToParts()` method allows locale-aware formatting of strings produced by `NumberFormat` formatters.

Syntax
------

    formatToParts()
    formatToParts(number)

### Parameters

 `number` <span class="badge inline optional">Optional</span>   
A [`Number`](../../number) or [`BigInt`](../../bigint) to format.

### Return value

An [`Array`](../../array) of objects containing the formatted number in parts.

Description
-----------

The `formatToParts()` method is useful for custom formatting of number strings. It returns an [`Array`](../../array) of objects containing the locale-specific tokens from which it possible to build custom strings while preserving the locale-specific parts. The structure the `formatToParts()` method returns, looks like this:

    [
      { type: "integer", value: "3" },
      { type: "group", value: "." },
      { type: "integer", value: "500" }
    ]

Possible types are the following:

currency  
The currency string, such as the symbols "$" and "€" or the name "Dollar", "Euro" depending on how `currencyDisplay` is specified.

decimal  
The decimal separator string (".").

fraction  
The fraction number.

group  
The group separator string (",").

infinity  
The [`Infinity`](../../infinity) string ("∞").

integer  
The integer number.

literal  
Any literal strings or whitespace in the formatted number.

minusSign  
The minus sign string ("-").

nan  
The [`NaN`](../../nan) string ("NaN").

plusSign  
The plus sign string ("+").

percentSign  
The percent sign string ("%").

unit  
The unit string, such as the "l" or "litres", depending on how `unitDisplay` is specified.

Examples
--------

### Comparing format and formatToParts

`NumberFormat` outputs localized, opaque strings that cannot be manipulated directly:

    var number = 3500;

    var formatter = new Intl.NumberFormat('de-DE', {
      style: 'currency',
      currency: 'EUR'
    });

    formatter.format(number);
    // "3.500,00 €"

However, in many User Interfaces there is a desire to customize the formatting of this string. The `formatToParts` method enables locale-aware formatting of strings produced by `NumberFormat` formatters by providing you the string in parts:

    formatter.formatToParts(number);

    // return value:
    [
      { type: "integer",  value: "3"   },
      { type: "group",    value: "."   },
      { type: "integer",  value: "500" },
      { type: "decimal",  value: ","   },
      { type: "fraction", value: "00"  },
      { type: "literal",  value: " "   },
      { type: "currency", value: "€"   }
    ]

Now the information is available separately and it can be formatted and concatenated again in a customized way. For example by using [`Array.prototype.map()`](../../array/map), [arrow functions](../../../functions/arrow_functions), a [switch statement](../../../statements/switch), [template literals](../../../template_literals), and [`Array.prototype.reduce()`](../../array/reduce).

    var numberString = formatter.formatToParts(number).map(({type, value}) => {
      switch (type) {
        case 'currency': return `<strong>${value}</strong>`;
        default : return value;
      }
    }).reduce((string, part) => string + part);

This will make the currency bold, when using the `formatToParts()` method.

    console.log(numberString);
    // "3.500,00 <strong>€</strong>"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma402/#sec-intl.numberformat.prototype.formattoparts">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sec-intl.numberformat.prototype.formattoparts</span></a></td></tr></tbody></table>

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

`formatToParts`

64

12

58

No

51

13

64

64

58

47

13

9.0

See also
--------

-   [`Intl.NumberFormat`](../numberformat)
-   [`Intl.NumberFormat.prototype.format`](format)
-   Formatting dates: [`Intl.DateTimeFormat.prototype.formatToParts()`](../datetimeformat/formattoparts)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/formatToParts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/formatToParts</a>
