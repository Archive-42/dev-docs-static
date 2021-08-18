RegExp.prototype\[@@split\]()
=============================

The `[@@split]()` method splits a [`String`](../string) object into an array of strings by separating the string into substrings.

Syntax
------

    regexp[Symbol.split](str[, limit])

### Parameters

`str`  
The target of the split operation.

 `limit` <span class="badge inline optional">Optional</span>   
Integer specifying a limit on the number of splits to be found. The `[@@split]()` method still splits on every match of `this` RegExp pattern (or, in the Syntax above, `regexp`), until the number of split items match the `limit` or the string falls short of `this` pattern.

### Return value

An [`Array`](../array) containing substrings as its elements.

Description
-----------

This method is called internally in [`String.prototype.split()`](../string/split) if its `separator` argument is an object that has a `@@split` method, such as a [`RegExp`](../regexp). For example, the following two examples return the same result.

    'a-b-c'.split(/-/);

    /-/[Symbol.split]('a-b-c');

This method exists for customizing the behavior of `split()` in `RegExp` subclass.

Examples
--------

### Direct call

This method can be used in almost the same way as [`String.prototype.split()`](../string/split), except the different `this` and the different order of arguments.

    let re = /-/g;
    let str = '2016-01-02';
    let result = re[Symbol.split](str);
    console.log(result);  // ["2016", "01", "02"]

### Using @@split in subclasses

Subclasses of [`RegExp`](../regexp) can override the `[@@split]()` method to modify the default behavior.

    class MyRegExp extends RegExp {
      [Symbol.split](str, limit) {
        let result = RegExp.prototype[Symbol.split].call(this, str, limit);
        return result.map(x => "(" + x + ")");
      }
    }

    let re = new MyRegExp('-');
    let str = '2016-01-02';
    let result = str.split(re); // String.prototype.split calls re[@@split].
    console.log(result); // ["(2016)", "(01)", "(02)"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype-@@split">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype-@@split</span></a></td></tr></tbody></table>

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

`@@split`

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

-   [`String.prototype.split()`](../string/split)
-   [`RegExp.prototype[@@match]()`](@@match)
-   [`RegExp.prototype[@@replace]()`](@@replace)
-   [`RegExp.prototype[@@search]()`](@@search)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.test()`](test)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@split" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@split</a>
