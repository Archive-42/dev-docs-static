HTMLFontElement.size
====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete `HTMLFontElement.size` property is a [`DOMString`](../domstring) that reflects the [`size`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font#attr-size) HTML attribute. It contains either an integer number in the range of 1-7 or a relative value to increase/decrease the value of the [`size`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont#attr-size) attribute of the [`<basefont>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont) element.

The format of the string must follow one of the following HTML microsyntaxes:

<table><thead><tr class="header"><th>Microsyntax</th><th>Description</th><th>Examples</th></tr></thead><tbody><tr class="odd"><td>Valid size number string</td><td><em>integer number in the range of 1-7</em></td><td><code>6</code></td></tr><tr class="even"><td>Relative size string</td><td><em>+x or -x, where x is the number relative to the value of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont#attr-size"><code>size</code></a> attribute of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont"><code>&lt;basefont&gt;</code></a> element</em><br />
<em>(the result should be in the same range of 1-7)</em></td><td><code>+2     -1</code></td></tr></tbody></table>

Syntax
------

    sizeString = fontObj.size;
    fontObj.size = sizeString;

Examples
--------

    // Assumes there is <font id="f"> element in the HTML

    var f = document.getElementById("f");
    f.size = "6";

Specifications
--------------

The &lt;font&gt; tag is not supported in HTML5 and as a result neither is `<font>.size `.

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

`size`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   The [`HTMLFontElement`](../htmlfontelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/size</a>
