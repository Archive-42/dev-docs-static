Symbol.split
============

The `Symbol.split` well-known symbol specifies the method that splits a string at the indices that match a regular expression. This function is called by the [`String.prototype.split()`](../string/split) method.

For more information, see [`RegExp.prototype[@@split]()`](../regexp/@@split) and [`String.prototype.split()`](../string/split).

Property attributes of `Symbol.split`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Custom reverse split

    class ReverseSplit {
      [Symbol.split](string) {
        const array = string.split(' ');
        return array.reverse();
      }
    }

    console.log('Another one bites the dust'.split(new ReverseSplit()));
    // expected output: [ "dust", "the", "bites", "one", "Another" ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.split">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.split</span></a></td></tr></tbody></table>

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

`split`

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
-   [`Symbol.search`](search)
-   [`RegExp.prototype[@@split]()`](../regexp/@@split)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split</a>
