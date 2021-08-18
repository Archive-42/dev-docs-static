String.prototype.at()
=====================

The `at()` method takes an integer value and returns a new [`String`](../string) consisting of the single UTF-16 code unit located at the specified offset. This method allows for positive and negative integers. Negative integers count back from the last string character.

Syntax
------

    at(index)

### Parameters

`index`  
The index (position) of the string character to be returned. Supports relative indexing from the end of the string when passed a negative index; i.e. if a negative number is used, the character returned will be found by counting back from the end of the string.

### Return value

A [`String`](../string) consisting of the single UTF-16 code unit located at the specified position. Returns [`undefined`](../undefined) if the given index can not be found.

Examples
--------

### Return the last character of a string

The following example provides a function which returns the last character found in a specified string.

    // A function which returns the last character of a given string
    function returnLast(arr) {
      return arr.at(-1);
    }

    let invoiceRef = 'myinvoice01';

    console.log( returnLast(invoiceRef) );
    // Logs: '1'

    invoiceRef = 'myinvoice02';

    console.log( returnLast(invoiceRef) );
    // Logs: '2'

### Comparing methods

Here we compare different ways to select the penultimate (last but one) character of a [`String`](../string). Whilst all below methods are valid, it highlights the succinctness and readability of the `at()` method.

    const myString = 'Every green bus drives fast.';

    // Using length property and charAt() method
    const lengthWay = myString.charAt(myString.length-2);
    console.log(lengthWay); // Logs: 't'

    // Using slice() method
    const sliceWay = myString.slice(-2, -1);
    console.log(sliceWay); // Logs: 't'

    // Using at() method
    const atWay = myString.at(-2);
    console.log(atWay); // Logs: 't'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/proposal-relative-indexing-method/#sec-string-prototype-additions">Relative Indexing Method (Relative Indexing Method)<br />
<span class="small">#sec-string-prototype-additions</span></a></td></tr></tbody></table>

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

`at`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [A polyfill for the at() method](https://github.com/tc39/proposal-relative-indexing-method#polyfill).
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)
-   [`String.prototype.charCodeAt()`](charcodeat)
-   [`String.prototype.codePointAt()`](codepointat)
-   [`String.prototype.split()`](split)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at</a>
