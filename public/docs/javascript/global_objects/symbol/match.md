Symbol.match
============

The `Symbol.match` well-known symbol specifies the matching of a regular expression against a string. This function is called by the [`String.prototype.match()`](../string/match) method.

Description
-----------

This function is also used to identify if objects have the behavior of regular expressions. For example, the methods [`String.prototype.startsWith()`](../string/startswith), [`String.prototype.endsWith()`](../string/endswith) and [`String.prototype.includes()`](../string/includes), check if their first argument is a regular expression and will throw a [`TypeError`](../typeerror) if they are. Now, if the `match` symbol is set to `false` (or a [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value), it indicates that the object is not intended to be used as a regular expression object.

Property attributes of `Symbol.match`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Disabling the `isRegExp` check

The following code will throw a [`TypeError`](../typeerror):

    '/bar/'.startsWith(/bar/);

    // Throws TypeError, as /bar/ is a regular expression
    // and Symbol.match is not modified.

However, if you set `Symbol.match` to `false`, the `isRegExp` check (that uses the `match` property) will indicate that the object is not a regular expression object. The methods `startsWith` and `endsWith` won't throw a `TypeError` as a consequence.

    var re = /foo/;
    re[Symbol.match] = false;
    '/foo/'.startsWith(re); // true
    '/baz/'.endsWith(re);   // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.match">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.match</span></a></td></tr></tbody></table>

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

`match`

50

79

40

No

37

10

50

50

40

37

10

5.0

See also
--------

-   [`Symbol.replace`](replace)
-   [`Symbol.search`](search)
-   [`Symbol.split`](split)
-   [`RegExp.prototype[@@match]()`](../regexp/@@match)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match</a>
