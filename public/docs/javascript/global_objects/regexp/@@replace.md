RegExp.prototype\[@@replace\]()
===============================

The `[@@replace]()` method replaces some or all matches of a `this` pattern in a string by a `replacement`, and returns the result of the replacement as a new string. The `replacement` can be a string or a function to be called for each match.

Syntax
------

    regexp[Symbol.replace](str, newSubStr|function)

### Parameters

`str`  
A [`String`](../string) that is a target of the replacement.

 `newSubStr` (replacement)  
The [`String`](../string) that replaces the substring. A number of special replacement patterns are supported; see the [Specifying a string as a parameter](../string/replace#specifying_a_string_as_a_parameter) section in [`String.prototype.replace()`](../string/replace) page.

 `function` (replacement)  
A function to be invoked to create the new substring. The arguments supplied to this function are described in the [Specifying a function as a parameter](../string/replace#specifying_a_function_as_a_parameter) section in [`String.prototype.replace()`](../string/replace) page.

### Return value

A new string with some or all matches of a pattern replaced by a replacement.

Description
-----------

This method is called internally in [`String.prototype.replace()`](../string/replace) if the `pattern` argument is a [`RegExp`](../regexp) object. For example, following two examples return same result.

    'abc'.replace(/a/, 'A');

    /a/[Symbol.replace]('abc', 'A');

This method exists for customizing replace behavior in `RegExp` subclass.

If pattern argument is **not** a [`RegExp`](../regexp) object, [`String.prototype.replace()`](../string/replace) doesn't call this method, nor creates a [`RegExp`](../regexp) object.

Examples
--------

### Direct call

This method can be used in almost the same way as [`String.prototype.replace()`](../string/replace), except the different `this` and the different arguments order.

    var re = /-/g;
    var str = '2016-01-01';
    var newstr = re[Symbol.replace](str, '.');
    console.log(newstr);  // 2016.01.01

### Using @@replace in subclasses

Subclasses of [`RegExp`](../regexp) can override the `[@@replace]()` method to modify the default behavior.

    class MyRegExp extends RegExp {
      constructor(pattern, flags, count) {
        super(pattern, flags);
        this.count = count;
      }
      [Symbol.replace](str, replacement) {
        // Perform @@replace |count| times.
        var result = str;
        for (var i = 0; i < this.count; i++) {
          result = RegExp.prototype[Symbol.replace].call(this, result, replacement);
        }
        return result;
      }
    }

    var re = new MyRegExp('\\d', '', 3);
    var str = '01234567';
    var newstr = str.replace(re, '#'); // String.prototype.replace calls re[@@replace].
    console.log(newstr); // ###34567

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype-@@replace">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype-@@replace</span></a></td></tr></tbody></table>

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

`@@replace`

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

-   [`String.prototype.replace()`](../string/replace)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype[@@split]()`](@@split)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@replace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@replace</a>
