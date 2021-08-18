RegExp.prototype\[@@match\]()
=============================

The `[@@match]()` method retrieves the matches when matching a *string* against a *regular expression*.

Syntax
------

    regexp[Symbol.match](str)

### Parameters

`str`  
A [`String`](../string) that is a target of the match.

### Return value

An [`Array`](../array) containing the entire match result and any parentheses-captured matched results, or [`null`](../null) if there were no matches.

Description
-----------

This method is called internally in [`String.prototype.match()`](../string/match).

For example, the following two examples return same result.

    'abc'.match(/a/);

    /a/[Symbol.match]('abc');

This method exists for customizing match behavior within `RegExp` subclasses.

Examples
--------

### Direct call

This method can be used in *almost* the same way as [`String.prototype.match()`](../string/match), except the different `this` and the different arguments order.

    let re = /[0-9]+/g;
    let str = '2016-01-02';
    let result = re[Symbol.match](str);
    console.log(result);  // ["2016", "01", "02"]

### Using `@@match` in subclasses

Subclasses of [`RegExp`](../regexp) can override the `[@@match]()` method to modify the default behavior.

    class MyRegExp extends RegExp {
      [Symbol.match](str) {
        let result = RegExp.prototype[Symbol.match].call(this, str);
        if (!result) return null;
        return {
          group(n) {
            return result[n];
          }
        };
      }
    }

    let re = new MyRegExp('([0-9]+)-([0-9]+)-([0-9]+)');
    let str = '2016-01-02';
    let result = str.match(re); // String.prototype.match calls re[@@match].
    console.log(result.group(1)); // 2016
    console.log(result.group(2)); // 01
    console.log(result.group(3)); // 02

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype-@@match">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype-@@match</span></a></td></tr></tbody></table>

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

`@@match`

50

13

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

-   [`String.prototype.match()`](../string/match)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@match</a>
