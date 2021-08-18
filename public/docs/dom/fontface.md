# FontFace

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FontFace` interface represents a single usable font face. It allows control of the source of the font face, being a URL to an external resource, or a buffer; it also allows control of when the font face is loaded and its current status.

## Constructor

[`FontFace()`](fontface/fontface)  
Constructs and returns a new `FontFace` object, built from an external resource described by an URL or from an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Properties

_This interface doesn't inherit any property._

[`FontFace.display`](fontface/display)  
A [`CSSOMString`](cssomstring) that determines how a font face is displayed based on whether and when it is downloaded and ready to use.

[`FontFace.family`](fontface/family)  
A [`CSSOMString`](cssomstring) that retrieves or sets the _family_ of the font. It is equivalent to the [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family) descriptor.

[`FontFace.featureSettings`](fontface/featuresettings)  
A [`CSSOMString`](cssomstring) that retrieves or sets infrequently used font features that are not available from a font's variant properties. It is equivalent to the <span class="page-not-created">`font-feature-settings`</span> descriptor.

[`FontFace.loaded`](fontface/loaded) <span class="badge inline readonly">Read only </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the current `FontFace` object when the font specified in the object's constructor is done loading or rejects with a `SyntaxError`.

[`FontFace.status`](fontface/status) <span class="badge inline readonly">Read only </span>  
Returns an enumerated value indicating the status of the font, one of `"unloaded"`, `"loading"`, `"loaded"`, or `"error"`.

[`FontFace.stretch`](fontface/stretch)  
A [`CSSOMString`](cssomstring) that retrieves or sets how the font _stretches_. It is equivalent to the [`font-stretch`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-stretch) descriptor.

[`FontFace.style`](fontface/style)  
A [`CSSOMString`](cssomstring) that retrieves or sets the _style_ of the font. It is equivalent to the [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-style) descriptor.

[`FontFace.unicodeRange`](fontface/unicoderange)  
A [`CSSOMString`](cssomstring) that retrieves or sets the _range of unicode codepoints_ encompassing the font. It is equivalent to the [`unicode-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range) descriptor.

[`FontFace.variant`](fontface/variant)  
A [`CSSOMString`](cssomstring) that retrieves or sets the _variant_ of the font. It is equivalent to the [`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variant) descriptor.

[`FontFace.weight`](fontface/weight)  
A [`CSSOMString`](cssomstring) that contains the _weight_ of the font. It is equivalent to the [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-weight) descriptor.

## Methods

_This interface doesn't inherit any method._

[`FontFace.load()`](fontface/load)  
Loads a font based on current object's constructor-passed requirements, including a location or source buffer, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the current FontFace object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#fontface-interface">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`FontFace`

35

79

41

No

22

10

37

35

41

22

10

4.0

`FontFace`

35

79

41

No

22

10

37

35

41

22

10

4.0

`ascentOverride`

87

87

No

No

73

No

87

87

No

No

No

14.0

`descentOverride`

87

87

No

No

73

No

87

87

No

No

No

14.0

`display`

60

79

58

No

47

10

60

60

No

44

10

8.0

`family`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`featureSettings`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`lineGapOverride`

87

87

No

No

73

No

87

87

No

No

No

14.0

`load`

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

79

Yes

No

Yes

10

45

37-45

Before WebView 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

Yes

Yes

10

5.0

4.0-5.0

Before Samsung Internet 5.0, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

`loaded`

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

79

Yes

No

Yes

10

45

37-45

Before WebView 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

45

35-45

Before Chrome 45, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

Yes

Yes

10

5.0

4.0-5.0

Before Samsung Internet 5.0, the returned promise resolved with void instead of a `FontFace` object as required by the specification.

`status`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`stretch`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`style`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`unicodeRange`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`variant`

35

79

Yes

No

Yes

No

37

35

Yes

Yes

No

4.0

`variationSettings`

No

No

62

No

No

No

No

No

62

No

No

No

`weight`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

`worker_support`

69

79

?

No

?

?

69

69

?

?

?

10.0

## See also

- [@font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace</a>
