String() constructor
====================

The `String` constructor is used to create a new [`String`](../string) object. When called instead as a function, it performs type conversion to a [primitive string](https://developer.mozilla.org/en-US/docs/Glossary/String), which is usually more useful.

Syntax
------

    new String(thing)
    String(thing)

### Parameters

`thing`  
Anything to be converted to a string.

Examples
--------

### String constructor and String function

String function and String constructor produce different results:

    typeof String('Hello world'); // string
    typeof new String('Hello world'); // object

Here, the function produces a string (the [primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) type) as promised. However, the constructor produces an instance of the type String (an object wrapper) and that's why you rarely want to use the String constructor at all.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string-constructor</span></a></td></tr></tbody></table>

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

`String`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [Text formatting in the JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Text_formatting)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String</a>
