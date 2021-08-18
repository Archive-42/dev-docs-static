Symbol.search
=============

The `Symbol.search` well-known symbol specifies the method that returns the index within a string that matches the regular expression. This function is called by the [`String.prototype.search()`](../string/search) method.

For more information, see [`RegExp.prototype[@@search]()`](../regexp/@@search) and [`String.prototype.search()`](../string/search).

Property attributes of `Symbol.search`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Custom string search

    class caseInsensitiveSearch {
      constructor(value) {
        this.value = value.toLowerCase();
      }
      [Symbol.search](string) {
        return string.toLowerCase().indexOf(this.value);
      }
    }

    console.log('foobar'.search(new caseInsensitiveSearch('BaR')));
    // expected output: 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.search">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.search</span></a></td></tr></tbody></table>

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

`search`

50

79

49

No

37

10

50

50

49

37

10

5.0

See also
--------

-   [`Symbol.match`](match)
-   [`Symbol.replace`](replace)
-   [`Symbol.split`](split)
-   [`RegExp.prototype[@@search]()`](../regexp/@@search)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/search" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/search</a>
