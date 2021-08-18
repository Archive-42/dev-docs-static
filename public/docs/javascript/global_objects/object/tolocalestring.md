Object.prototype.toLocaleString()
=================================

The `toLocaleString()` method returns a string representing the object. This method is meant to be overridden by derived objects for locale-specific purposes.

Syntax
------

    toLocaleString()

### Return value

A string representing the object.

Description
-----------

[`Object`](../object)'s `toLocaleString` returns the result of calling [`toString()`](tostring).

This function is provided to give objects a generic `toLocaleString` method, even though not all may use it. See the list below.

### Objects overriding toLocaleString

-   [`Array`](../array): [`Array.prototype.toLocaleString()`](../array/tolocalestring)
-   [`Number`](../number): [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   [`Date`](../date): [`Date.prototype.toLocaleString()`](../date/tolocalestring)
-   [`TypedArray`](../typedarray): [`TypedArray.prototype.toLocaleString()`](../typedarray/tolocalestring)
-   [`BigInt`](../bigint): [`BigInt.prototype.toLocaleString()`](../bigint/tolocalestring)

Examples
--------

### Array toLocaleString() override

On [`Array`](../array) objects, [`toLocaleString()`](../array/tolocalestring) can be used to print array values as a string, optionally with locale-specific identifiers (such as currency symbols) appended to them:

For example:

    const testArray = [4, 7, 10];

    let euroPrices = testArray.toLocaleString('fr', { style: 'currency', currency: 'EUR'});
    // "4,00 €,7,00 €,10,00 €"

### Date toLocaleString() override

On [`Date`](../date) objects, [`toLocaleString()`](../date/tolocalestring) is used to print out date displays more suitable for specific locales:

For example:

    const testDate = new Date(Date.now());
    // "Date Fri May 29 2020 18:04:24 GMT+0100 (British Summer Time)"

    let deDate = testDate.toLocaleString('de');
    // "29.5.2020, 18:04:24"

    var frDate = testDate.toLocaleString('fr');
    //"29/05/2020 à 18:04:24"

### Number toLocaleString() override

On [`Number`](../number) objects, [`toLocaleString()`](../number/tolocalestring) is used to print out number displays more suitable for specific locales, e.g. with the correct separators:

For example:

    const testNumber = 2901234564;
    // "2901234564"

    let deNumber = testNumber.toLocaleString('de');
    // "2.901.234.564"

    let frNumber = testNumber.toLocaleString('fr');
    // "2 901 234 564"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.prototype.tolocalestring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.prototype.tolocalestring</span></a></td></tr></tbody></table>

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

`toLocaleString`

1

12

1

5.5

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [`Object.prototype.toString()`](tostring)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toLocaleString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toLocaleString</a>
