Symbol.replace
==============

The `Symbol.replace` well-known symbol specifies the method that replaces matched substrings of a string. This function is called by the [`String.prototype.replace()`](../string/replace) method.

For more information, see [`RegExp.prototype[@@replace]()`](../regexp/@@replace) and [`String.prototype.replace()`](../string/replace).

Property attributes of `Symbol.replace`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Using Symbol.replace

    class CustomReplacer {
      constructor(value) {
        this.value = value;
      }
      [Symbol.replace](string) {
        return string.replace(this.value, '#!@?');
      }
    }

    console.log('football'.replace(new CustomReplacer('foo')));
    // expected output: "#!@?tball"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.replace">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.replace</span></a></td></tr></tbody></table>

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

`replace`

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
-   [`Symbol.search`](search)
-   [`Symbol.split`](split)
-   [`RegExp.prototype[@@replace]()`](../regexp/@@replace)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/replace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/replace</a>
