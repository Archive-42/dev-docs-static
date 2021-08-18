String.prototype.includes()
===========================

The `includes()` method performs a case-sensitive search to determine whether one string may be found within another string, returning `true` or `false` as appropriate.

Syntax
------

    includes(searchString)
    includes(searchString, position)

### Parameters

`searchString`  
A string to be searched for within `str`.

 `position` <span class="badge inline optional">Optional</span>   
The position within the string at which to begin searching for `searchString`. (Defaults to `0`.)

### Return value

`true` if the search string is found anywhere within the given string; otherwise, `false` if not.

Description
-----------

This method lets you determine whether or not a string includes another string.

### Case-sensitivity

The `includes()` method is case sensitive. For example, the following expression returns `false`:

    'Blue Whale'.includes('blue')  // returns false

Polyfill
--------

This method has been added to the ECMAScript 2015 specification and may not be available in all JavaScript implementations yet.

However, you can easily polyfill this method:

    if (!String.prototype.includes) {
      String.prototype.includes = function(search, start) {
        'use strict';

        if (search instanceof RegExp) {
          throw TypeError('first argument must not be a RegExp');
        }
        if (start === undefined) { start = 0; }
        return this.indexOf(search, start) !== -1;
      };
    }

Examples
--------

### Using `includes()`

    const str = 'To be, or not to be, that is the question.'

    console.log(str.includes('To be'))        // true
    console.log(str.includes('question'))     // true
    console.log(str.includes('nonexistent'))  // false
    console.log(str.includes('To be', 1))     // false
    console.log(str.includes('TO BE'))        // false
    console.log(str.includes(''))             // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.includes">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype.includes</span></a></td></tr></tbody></table>

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

`includes`

41

12

40

18-48

No

28

9

41

41

40

18-48

28

9

4.0

See also
--------

-   [`Array.prototype.includes()`](../array/includes)
-   [`TypedArray.prototype.includes()`](../typedarray/includes)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)
-   [`String.prototype.startsWith()`](startswith)
-   [`String.prototype.endsWith()`](endswith)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes</a>
