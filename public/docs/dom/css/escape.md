# CSS.escape()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSS.escape()` static method returns a [`CSSOMString`](../cssomstring) containing the escaped string passed as parameter, mostly for use as part of a CSS selector.

## Syntax

    escapedStr = CSS.escape(str);

### Parameters

_str_  
The [`CSSOMString`](../cssomstring) to be escaped.

## Examples

### Basic results

    CSS.escape(".foo#bar")        // "\.foo\#bar"
    CSS.escape("()[]{}")          // "\(\)\[\]\{\}"
    CSS.escape('--a')             // "--a"
    CSS.escape(0)                 // "\30 ", the Unicode code point of '0' is 30
    CSS.escape('\0')              // "\ufffd", the Unicode REPLACEMENT CHARACTER

### In context uses

To escape a string for use as part of a selector, the `escape()` method can be used:

    var element = document.querySelector('#' + CSS.escape(id) + ' > img');

The `escape()` method can also be used for escaping strings, although it escapes characters that don't strictly need to be escaped:

    var element = document.querySelector('a[href="#' + CSS.escape(fragment) + '"]');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-css.escape()-method">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSS.escape()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`escape`

46

79

31

No

33

10

46

46

31

33

10

5.0

## See also

- The [`CSS`](../css) interface where this static method resides.
- [A polyfill for the CSS.escape](https://github.com/mathiasbynens/CSS.escape/blob/master/css.escape.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/escape" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS/escape</a>
