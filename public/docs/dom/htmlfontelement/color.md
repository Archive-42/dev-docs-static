# HTMLFontElement.color

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete ` HTMLFontElement``.color ` property is a [`DOMString`](../domstring) that reflects the [`color`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font#attr-color) HTML attribute, containing either a named color or a color specified in the hexadecimal \#RRGGBB format.

The format of the string must follow one of the following HTML microsyntaxes:

<table><thead><tr class="header"><th>Microsyntax</th><th>Description</th><th>Examples</th></tr></thead><tbody><tr class="odd"><td>Valid name color string</td><td><em>nameOfColor (case insensitive)</em></td><td><code>Green</code><br />
<code>green</code><br />
<code>GREEN</code></td></tr><tr class="even"><td>Valid hex color string</td><td><em>in</em> <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb"><code>rgb format</code></a><em>: #RRGGBB</em></td><td><code>#008000</code></td></tr><tr class="odd"><td>RGB using decimal values</td><td><em>rgb(x,x,x) (x in 0-255 range)</em></td><td><code>rgb(0,128,0)</code></td></tr></tbody></table>

## Syntax

    colorString = fontObj.color;
    fontObj.color = colorString;

## Examples

    // Assumes there is <font id="f"> element in the HTML

    var f = document.getElementById("f");
    f.color = "green";

## Specifications

The &lt;font&gt; tag is not supported in HTML5 and as a result neither is `<font>.color`.

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

`color`

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

## See also

- The [`HTMLFontElement`](../htmlfontelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/color</a>
