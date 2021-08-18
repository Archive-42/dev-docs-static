Reflect.apply()
===============

The static `Reflect.apply()` method calls a target function with arguments as specified.

Syntax
------

    Reflect.apply(target, thisArgument, argumentsList)

### Parameters

`target`  
The target function to call.

`thisArgument`  
The value of `this` provided for the call to `target`.

`argumentsList`  
An array-like object specifying the arguments with which `target` should be called.

### Return value

The result of calling the given `target` function with the specified `this` value and arguments.

### Exceptions

A [`TypeError`](../typeerror), if the `target` is not callable.

Description
-----------

In ES5, you typically use the [`Function.prototype.apply()`](../function/apply) method to call a function with a given `this` value and `arguments` provided as an array (or an [array-like object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)).

    Function.prototype.apply.call(Math.floor, undefined, [1.75]);

With `Reflect.apply()` this becomes less verbose and easier to understand.

Examples
--------

### Using Reflect.apply()

    Reflect.apply(Math.floor, undefined, [1.75]);
    // 1;

    Reflect.apply(String.fromCharCode, undefined, [104, 101, 108, 108, 111])
    // "hello"

    Reflect.apply(RegExp.prototype.exec, /ab/, ['confabulation']).index
    // 4

    Reflect.apply(''.charAt, 'ponies', [3])
    // "i"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-reflect.apply">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-reflect.apply</span></a></td></tr></tbody></table>

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

`apply`

49

12

42

No

36

10

49

49

42

36

10

5.0

See also
--------

-   [`Reflect`](../reflect)
-   [`Function.prototype.apply()`](../function/apply)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/apply" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/apply</a>
