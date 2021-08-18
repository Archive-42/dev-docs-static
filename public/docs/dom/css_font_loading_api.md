# CSS Font Loading API

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The CSS Font Loading API provides events and interfaces for dynamically loading font resources.

**Note:** This feature is available in [Web Workers](web_workers_api) (`self.fonts` provides access to [`FontFaceSet`](fontfaceset)).

## Interfaces

[`FontFace`](fontface)  
Represents a single usable font face.

[`FontFaceSet`](fontfaceset)  
An interface loading font faces and checking their download statuses.

<span class="page-not-created">`FontFaceSource`</span>  
A [mixin](https://developer.mozilla.org/en-US/docs/Glossary/Mixin) providing all of the fonts used in font-related operations, unless defined otherwise. It defines the <span class="page-not-created">`FontFaceSources.fonts`</span> property available to [`Document`](document) and [`WorkerGlobalScope`](workerglobalscope).

[`FontFaceSetLoadEvent`](fontfacesetloadevent)  
Fired whenever a [`FontFaceSet`](fontfaceset) loads.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/">CSS Font Loading Module Level 3</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSS_Font_Loading_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API</a>
