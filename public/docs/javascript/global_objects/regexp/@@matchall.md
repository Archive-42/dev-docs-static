RegExp.prototype\[@@matchAll\]()
================================

The `[@@matchAll]` method returns all matches of the regular expression against a string.

Syntax
------

    regexp[Symbol.matchAll](str)

### Parameters

`str`  
A [`String`](../string) that is a target of the match.

### Return value

An [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators).

Description
-----------

This method is called internally in [`String.prototype.matchAll()`](../string/matchall). For example, the following two examples return same result.

    'abc'.matchAll(/a/);

    /a/[Symbol.matchAll]('abc');

This method exists for customizing the behavior of `matchAll()` in [`RegExp`](../regexp) subclasses.

Examples
--------

### Direct call

This method can be used in almost the same way as [`String.prototype.matchAll()`](../string/matchall), except for the different value of `this` and the different order of arguments.

    let re = /[0-9]+/g;
    let str = '2016-01-02';
    let result = re[Symbol.matchAll](str);

    console.log(Array.from(result, x => x[0]));
    // ["2016", "01", "02"]

### Using @@matchAll in subclasses

Subclasses of [`RegExp`](../regexp) can override the `[@@matchAll]()` method to modify the default behavior.

For example, to return an [`Array`](../array) instead of an [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators):

    class MyRegExp extends RegExp {
      [Symbol.matchAll](str) {
        const result = RegExp.prototype[Symbol.matchAll].call(this, str);
        if (!result) {
          return null;
        } else {
          return Array.from(result);
        }
      }
    }

    const re = new MyRegExp('([0-9]+)-([0-9]+)-([0-9]+)', 'g');
    const str = '2016-01-02|2019-03-07';
    const result = str.matchAll(re);
    console.log(result[0]); // [ "2016-01-02", "2016", "01", "02" ]
    console.log(result[1]); // [ "2019-03-07", "2019", "03", "07" ]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp-prototype-matchall">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp-prototype-matchall</span></a></td></tr></tbody></table>

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

`@@matchAll`

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

5.0

See also
--------

-   [`String.prototype.matchAll()`](../string/matchall)
-   [`Symbol.matchAll`](../symbol/matchall)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@matchAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@matchAll</a>
