# CSS.paintWorklet (Static property)

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`paintWorklet` is a static, read-only property of the [`CSS`](../css) interface that provides access to the [`PaintWorklet`](../paintworklet), which programmatically generates an image where a CSS property expects a file.

## Syntax

    var worklet = CSS.paintWorklet;

### Value

The [`PaintWorklet`](../paintworklet) object.

## Examples

The following example demonstrates loading a [`PaintWorklet`](../paintworklet) from its js file and does so by feature detection.

    <script>
      if ('paintWorklet' in CSS) {
        CSS.paintWorklet.addModule('checkerboard.js');
      }
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#dom-css-paintworklet">CSS Painting API Level 1<br />
<span class="small">The definition of 'paintWorklet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`paintWorklet`

65

79

No

No

52

No

65

65

No

47

No

9.0

## See also

- [CSS Painting API](../css_painting_api)
- [Houdini APIs](https://developer.mozilla.org/en-US/docs/Web/Houdini)
- [Houdini overview](https://developer.mozilla.org/en-US/docs/Web/Houdini/learn)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/paintWorklet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS/paintWorklet</a>
