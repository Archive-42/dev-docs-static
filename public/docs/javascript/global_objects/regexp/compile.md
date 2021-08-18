RegExp.prototype.compile()
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `compile``()` method is used to (re-)compile a regular expression during execution of a script. It is basically the same as the `RegExp` constructor.

Syntax
------

    compile(pattern, flags)

### Parameters

`pattern`  
The text of the regular expression.

`flags`  
If specified, flags can have any combination of the following values:

`g`  
global match

`i`  
ignore case

`m`  
multiline; treat beginning and end characters (^ and $) as working over multiple lines (i.e., match the beginning or end of *each* line (delimited by \\n or \\r), not only the very beginning or end of the whole input string)

`y`  
sticky; matches only from the index indicated by the `lastIndex` property of this regular expression in the target string (and does not attempt to match from any later indexes).

Description
-----------

The `compile` method is deprecated. You can just use the `RegExp` constructor to achieve the same effect.

Examples
--------

### Using `compile()`

The following example shows how to recompile a regular expression with a new pattern and a new flag.

    var regexObj = new RegExp('foo', 'gi');
    regexObj.compile('new foo', 'g');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-regexp.prototype.compile">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-regexp.prototype.compile</span></a></td></tr></tbody></table>

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

`compile`

1

12

1

4

6

3.1

1

18

4

10.1

2

1.0

See also
--------

-   [`RegExp`](../regexp)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/compile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/compile</a>
