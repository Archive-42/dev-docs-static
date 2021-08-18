RegExp.prototype\[@@search\]()
==============================

The `[@@search]()` method executes a search for a match between a `this` regular expression and a string.

Syntax
------

    regexp[Symbol.search](str)

### Parameters

`str`  
A [`String`](../string) that is a target of the search.

### Return value

integer  
If successful, `[@@search]()` returns the index of the first match of the regular expression inside the string. Otherwise, it returns -1.

Description
-----------

This method is called internally in [`String.prototype.search()`](../string/search). For example, the following two examples return the same result.

    'abc'.search(/a/);

    /a/[Symbol.search]('abc');

This method exists for customizing the search behavior in `RegExp` subclasses.

Examples
--------

### Direct call

This method can be used in almost the same way as [`String.prototype.search()`](../string/search), except the different `this` and the different arguments order.

    var re = /-/g;
    var str = '2016-01-02';
    var result = re[Symbol.search](str);
    console.log(result);  // 4

### Using @@search in subclasses

Subclass of [`RegExp`](../regexp) can override `[@@search]()` method to modify the behavior.

    class MyRegExp extends RegExp {
      constructor(str) {
        super(str)
        this.pattern = str;
      }
      [Symbol.search](str) {
        return str.indexOf(this.pattern);
      }
    }

    var re = new MyRegExp('a+b');
    var str = 'ab a+b';
    var result = str.search(re); // String.prototype.search calls re[@@search].
    console.log(result); // 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype-@@search">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype-@@search</span></a></td></tr></tbody></table>

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

`@@search`

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

-   [`String.prototype.search()`](../string/search)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@search" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@search</a>
