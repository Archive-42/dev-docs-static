# DOMQuad

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

A `DOMQuad` is a collection of four `DOMPoint`s defining the corners of an arbitrary quadrilateral. Returning `DOMQuad`s lets `getBoxQuads()` return accurate information even when arbitrary 2D or 3D transforms are present. It has a handy `bounds` attribute returning a `DOMRectReadOnly` for those cases where you just want an axis-aligned bounding rectangle.

## Constructor

<span class="page-not-created">`DOMQuad.DOMQuad()`</span>  
Creates a new `DOMQuad` object.

## Properties

p1,p2,p3,p4 <span class="badge inline readonly">Read only </span>  
are [`DOMPoint`](dompoint) objects for each of the `DOMQuad` object's four corners.

## Methods

<span class="page-not-created">`DOMQuad.fromRect()`</span>  
Returns a new `DOMQuad` object based on the passed set of coordinates.

<span class="page-not-created">`DOMQuad.fromQuad()`</span>  
Returns a new `DOMQuad` object based on the passed set of coordinates.

<span class="page-not-created">`DOMQuad.getBounds()`</span>  
Returns a [`DOMRect`](domrect) object with the coordinates and dimensions of the `DOMQuad` object.

<span class="page-not-created">`DOMQuad.toJSON()`</span>  
Returns a JSON representation of the `DOMQuad` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMQuad">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMQuad' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMQuad`

61

79

31

No

48

11

61

61

31

45

11

8.0

`DOMQuad`

61

79

31

No

48

11

61

61

31

45

11

8.0

`fromQuad`

61

79

69

No

48

11

61

61

79

45

11

8.0

`fromRect`

61

79

69

No

48

11

61

61

79

45

11

8.0

`getBounds`

61

79

62

No

48

11

61

61

62

45

11

8.0

`p1`

61

79

31

Prior to Firefox 69, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

No

48

11

61

61

31

Prior to Firefox for Android 79, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

45

11

8.0

`p2`

61

79

31

Prior to Firefox 69, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

No

48

11

61

61

31

Prior to Firefox for Android 79, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

45

11

8.0

`p3`

61

79

31

Prior to Firefox 69, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

No

48

11

61

61

31

Prior to Firefox for Android 79, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

45

11

8.0

`p4`

61

79

31

Prior to Firefox 69, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

No

48

11

61

61

31

Prior to Firefox for Android 79, the default value of `p1` through `p4` was undefined; now `DOMQuadInit` defines these as `false`.

45

11

8.0

`toJSON`

61

79

62

No

48

11

61

61

62

45

11

8.0

`worker_support`

61

79

69

No

48

11

61

61

79

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMQuad" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMQuad</a>
