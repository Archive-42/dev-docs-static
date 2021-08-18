RegExp.prototype.global
=======================

The `global` property indicates whether or not the "`g`" flag is used with the regular expression. `global` is a read-only property of an individual regular expression instance.

Property attributes of `RegExp.prototype.global`

Writable

no

Enumerable

no

Configurable

yes

Description
-----------

The value of `global` is a [`Boolean`](../boolean) and `true` if the "`g`" flag was used; otherwise, `false`. The "`g`" flag indicates that the regular expression should be tested against all possible matches in a string. A regular expression defined as both `global` ("`g`") and `sticky` ("`y`") will ignore the `global` flag and perform sticky matches.

You cannot change this property directly.

Examples
--------

### Using global

    var regex = new RegExp('foo', 'g');

    console.log(regex.global);  // true

    var str = 'fooexamplefoo';

    var str1 = str.replace(regex, '');

    console.log(str1);  // Output: example

    var regex1 = new RegExp('foo');

    var str2 = str.replace(regex1, '');

    console.log(str2);  // Output: examplefoo

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-get-regexp.prototype.global">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'RegExp.prototype.global' in that specification.</span></a></td></tr></tbody></table>

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

`global`

1

12

1

5.5

5

1

1

18

4

10.1

1

1.0

`prototype_accessor`

48

12

38

5.5

35

1.3

48

48

38

35

1

5.0

See also
--------

-   [`RegExp.lastIndex`](lastindex)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global</a>
