Symbol.matchAll
===============

The `Symbol.matchAll` well-known symbol returns an iterator, that yields matches of the regular expression against a string. This function is called by the [`String.prototype.matchAll()`](../string/matchall) method.

Description
-----------

This Symbol is used for [`String.prototype.matchAll()`](../string/matchall) and specifically in [`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall). The following two examples return same result:

    'abc'.matchAll(/a/);

    /a/[Symbol.matchAll]('abc');

This method exists for customizing match behavior within [`RegExp`](../regexp) subclasses.

Property attributes of `Symbol.matchAll`

Writable

no

Enumerable

no

Configurable

no

Examples
--------

### Using Symbol.matchAll

    let re = /[0-9]+/g;
    let str = '2016-01-02|2019-03-07';

    const numbers = {
      *[Symbol.matchAll] (str) {
        for (const n of str.matchAll(/[0-9]+/g))
          yield n[0];
      }
    };

    console.log(Array.from(str.matchAll(numbers)));
    //  Array ["2016", "01", "02", "2019", "03", "07"]

See [`String.prototype.matchAll()`](../string/matchall) and [`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall) for more examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-symbol.matchall">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-symbol.matchall</span></a></td></tr></tbody></table>

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

`matchAll`

73

79

67

No

60

13

73

73

67

52

13

No

See also
--------

-   [`String.prototype.matchAll()`](../string/matchall)
-   [`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/matchAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/matchAll</a>
