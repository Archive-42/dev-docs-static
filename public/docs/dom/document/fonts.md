# Document.fonts

The `fonts` property of the [`Document`](../document) interface returns the [`FontFaceSet`](../fontfaceset) interface of the document.

## Syntax

    let fontFaceSet = document.fonts;

### Value

The returned value is the [`FontFaceSet`](../fontfaceset) interface of the document. The `FontFaceSet` interface is useful for loading new fonts, checking the status of previously loaded fonts etc.

## Examples

### Doing operation after all fonts are loaded

    document.fonts.ready.then(function() {
      // Any operation that needs to be done only after all the fonts
      // have finished loading can go here.
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#FontFaceSet-interface">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFaceSet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`fonts`

35

79

41

No

22

10

≤37

35

41

22

10

3.0

## See also

- [`FontFaceSet`](../fontfaceset) interface
- [`FontFace`](../fontface)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fonts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fonts</a>
