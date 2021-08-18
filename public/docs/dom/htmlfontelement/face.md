# HTMLFontElement.face

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete ` HTMLFontElement``.face ` property is a [`DOMString`](../domstring) that reflects the [`face`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font#attr-face) HTML attribute, containing a comma-separated list of one or more font names.

The document text, in the default style, is rendered as the first font face that the client's browser supports. If no font listed is installed on the local system, the browser typically defaults to the proportional or fixed-width font for that system.

The format of the string must follow one of the following HTML microsyntax:

<table><thead><tr class="header"><th>Microsyntax</th><th>Description</th><th>Examples</th></tr></thead><tbody><tr class="odd"><td>List of one or more valid font family names</td><td><em>A list of font names, that have to be present on the local system</em></td><td><code>courier,verdana</code></td></tr></tbody></table>

## Syntax

    faceString = fontObj.face;
    fontObj.face = faceString;

## Examples

    // Assumes there is <font id="f"> element in the HTML

    var f = document.getElementById("f");
    f.face = "arial";

## Specifications

The &lt;font&gt; tag is not supported in HTML5 and as a result neither is `<font>.face `.

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

`face`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/face" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement/face</a>
