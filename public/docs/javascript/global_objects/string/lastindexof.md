String.prototype.lastIndexOf()
==============================

The `lastIndexOf()` method returns the index within the calling [`String`](../string) object of the last occurrence of the specified value, searching backwards from `fromIndex`. Returns `-1` if the value is not found.

Syntax
------

    lastIndexOf(searchValue)
    lastIndexOf(searchValue, fromIndex)

### Parameters

`searchValue`  
A string representing the value to search for. If `searchValue` is an empty string, then `fromIndex` is returned.

 `fromIndex` <span class="badge inline optional">Optional</span>   
The index of the last character in the string to be considered as the beginning of a match. The default value is `+Infinity`. If `fromIndex >= str.length`, the whole string is searched. If `fromIndex < 0`, the behavior will be the same as if it would be `0`.

### Return value

The index of the last occurrence of `searchValue`; `-1` if not found.

Description
-----------

Characters in a string are indexed from left to right. The index of the first character is `0`, and the index of the last character is `str.length - 1`.

    'canal'.lastIndexOf('a');     // returns 3
    'canal'.lastIndexOf('a', 2);  // returns 1
    'canal'.lastIndexOf('a', 0);  // returns -1
    'canal'.lastIndexOf('x');     // returns -1
    'canal'.lastIndexOf('c', -5); // returns 0
    'canal'.lastIndexOf('c', 0);  // returns 0
    'canal'.lastIndexOf('');      // returns 5
    'canal'.lastIndexOf('', 2);   // returns 2

**Note:** `'abab'.lastIndexOf('ab', 2)` will return `2` and not `0`, as `fromIndex` limits only the beginning of the match.

### Case-sensitivity

The `lastIndexOf()` method is case sensitive. For example, the following expression returns `-1`:

    'Blue Whale, Killer Whale'.lastIndexOf('blue'); // returns -1

Examples
--------

### Using indexOf() and lastIndexOf()

The following example uses [`indexOf()`](indexof) and `lastIndexOf()` to locate values in the string "`Brave new world`".

    let anyString = 'Brave new world';

    console.log('The index of the first w from the beginning is ' + anyString.indexOf('w'));
    // logs 8
    console.log('The index of the first w from the end is ' + anyString.lastIndexOf('w'));
    // logs 10
    console.log('The index of "new" from the beginning is ' + anyString.indexOf('new'));
    // logs 6
    console.log('The index of "new" from the end is ' + anyString.lastIndexOf('new'));
    // logs 6

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.lastindexof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype.lastindexof</span></a></td></tr></tbody></table>

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

`lastIndexOf`

1

12

1

6

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

-   [`String.prototype.charAt()`](charat)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.split()`](split)
-   [`Array.prototype.indexOf()`](../array/indexof)
-   [`Array.prototype.lastIndexOf()`](../array/lastindexof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf</a>
