Window.find()
=============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Note:** Support for `Window.find()` might change in future versions of Gecko. See [bug 672395](https://bugzilla.mozilla.org/show_bug.cgi?id=672395).

The `Window.find()` method finds a string in a window.

Syntax
------

    window.find(aString, aCaseSensitive, aBackwards, aWrapAround,
                aWholeWord, aSearchInFrames, aShowDialog);

`aString`  
The text string for which to search.

`aCaseSensitive`  
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, specifies a case-sensitive search.

`aBackwards`  
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, specifies a backward search.

`aWrapAround`  
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, specifies a wrap around search.

 `aWholeWord` <span class="notecard inline warning">Unimplemented</span>   
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, specifies a whole word search. This is not implemented; see [bug 481513](https://bugzilla.mozilla.org/show_bug.cgi?id=481513).

`aSearchInFrames`  
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, specifies a search in frames.

### Returns

`true` if the string is found; otherwise, `false`.

Example
-------

### JavaScript

    findString = function findText(text) {
      alert("String \x22" + text + "\x22 found? " + window.find(text));
    }

### HTML

    <p>Apples, Bananas, and Oranges.</p>
    <button type="button" onClick='findString("Apples")'>Search for Apples</button>
    <button type="button" onClick='findString("Banana")'>Search for Banana</button>
    <button type="button" onClick='findString("Orange")'>Search for Orange</button>

### Result

Notes
-----

In some browsers, `Window.find()` selects (highlights) the found content on the site.

Specifications
--------------

This is not part of any specification.

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

`find`

1

79

1

No

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/find" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/find</a>
