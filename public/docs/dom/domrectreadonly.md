# DOMRectReadOnly

The `DOMRectReadOnly` interface specifies the standard properties used by [`DOMRect`](domrect) to define a rectangle whose properties are immutable.

## Constructor

[`DOMRectReadOnly()`](domrectreadonly/domrectreadonly)  
Defined to create a new `DOMRectReadOnly` object. Note that this constructor cannot be called by 3rd party JavaScript; doing so returns an `"Illegal constructor"` [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

## Properties

[`DOMRectReadOnly.x`](domrectreadonly/x) <span class="badge inline readonly">Read only </span>  
The x coordinate of the `DOMRect`'s origin.

[`DOMRectReadOnly.y`](domrectreadonly/y) <span class="badge inline readonly">Read only </span>  
The y coordinate of the `DOMRect`'s origin.

[`DOMRectReadOnly.width`](domrectreadonly/width) <span class="badge inline readonly">Read only </span>  
The width of the `DOMRect`.

[`DOMRectReadOnly.height`](domrectreadonly/height) <span class="badge inline readonly">Read only </span>  
The height of the `DOMRect`.

[`DOMRectReadOnly.top`](domrectreadonly/top) <span class="badge inline readonly">Read only </span>  
Returns the top coordinate value of the `DOMRect` (usually the same as `y`.)

[`DOMRectReadOnly.right`](domrectreadonly/right) <span class="badge inline readonly">Read only </span>  
Returns the right coordinate value of the `DOMRect` (usually the same as `x + width`).

[`DOMRectReadOnly.bottom`](domrectreadonly/bottom) <span class="badge inline readonly">Read only </span>  
Returns the bottom coordinate value of the `DOMRect` (usually the same as `y + height`).

[`DOMRectReadOnly.left`](domrectreadonly/left) <span class="badge inline readonly">Read only </span>  
Returns the left coordinate value of the `DOMRect` (usually the same as `x`).

## Static methods

[`DOMRectReadOnly.fromRect()`](domrectreadonly/fromrect)  
Creates a new `DOMRect` object with a given location and dimensions.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMRect">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMRectReadOnly' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMRectReadOnly`

61

79

12

31

No

Yes

48

10.1

61

61

31

45

10.3

8.0

`DOMRectReadOnly`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

`bottom`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`fromRect`

61

79

69

No

48

10.1

61

61

No

45

10.3

8.0

`height`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`left`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`right`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`toJSON`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

`top`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`width`

61

79

31

No

Implemented on the proprietary `ClientRect` interface.

48

10.1

61

61

31

45

10.3

8.0

`worker_support`

61

79

69

No

48

10.1

61

61

No

45

10.3

8.0

`x`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`y`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

## See also

- [`DOMPoint`](dompoint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly</a>
