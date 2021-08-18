SVGSVGElement
=============

The `SVGSVGElement` interface provides access to the properties of [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) elements, as well as methods to manipulate them. This interface contains also various miscellaneous commonly-used utility methods, such as matrix operations and the ability to control the time of redraw on visual rendering devices.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGraphicsElement`](svggraphicselement) and also implements the ones from [`SVGZoomAndPan`](svgzoomandpan), <span class="page-not-created">`SVGFitToViewBox`</span>, and [`WindowEventHandlers`](windoweventhandlers).*

 <span class="page-not-created">`SVGSVGElement.x`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `x` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

 <span class="page-not-created">`SVGSVGElement.y`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `y` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

 <span class="page-not-created">`SVGSVGElement.width`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `width` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

 <span class="page-not-created">`SVGSVGElement.height`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `height` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

<span class="page-not-created">`SVGSVGElement.contentScriptType`</span>  
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `contentScriptType` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

<span class="page-not-created">`SVGSVGElement.contentStyleType`</span>  
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `contentStyleType` attribute of the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element.

<span class="page-not-created">`SVGSVGElement.viewport`</span>  
An [`SVGRect`](svgrect) containing the position and size of the viewport (implicit or explicit) that corresponds to the given [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element. When the browser is actually rendering the content, then the position and size values represent the actual values when rendering. The position and size values are unitless values in the coordinate system of the parent element. If no parent element exists (i.e., [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element represents the root of the document tree), if this SVG document is embedded as part of another document (e.g., via the HTML [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) element), then the position and size are unitless values in the coordinate system of the parent document. (If the parent uses CSS or XSL layout, then unitless values represent pixel units for the current CSS or XSL viewport.)

 <span class="page-not-created">`SVGSVGElement.pixelUnitToMillimeterX`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A float representing the size of the pixel unit (as defined by CSS2) along the x-axis of the viewport, which represents a unit somewhere in the range of 70dpi to 120dpi, and, on systems that support this, might actually match the characteristics of the target medium. On systems where it is impossible to know the size of a pixel, a suitable default pixel size is provided.

 <span class="page-not-created">`SVGSVGElement.pixelUnitToMillimeterY`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A float representing the size of a pixel unit along the y-axis of the viewport.

 <span class="page-not-created">`SVGSVGElement.screenPixelToMillimeterX`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
User interface (UI) events in DOM Level 2 indicate the screen positions at which the given UI event occurred. When the browser actually knows the physical size of a "screen unit", this float attribute will express that information; otherwise, user agents will provide a suitable default value (such as `.28mm`).

 <span class="page-not-created">`SVGSVGElement.screenPixelToMillimeterY`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Corresponding size of a screen pixel along the y-axis of the viewport.

<span class="page-not-created">`SVGSVGElement.useCurrentView`</span>  
The initial view (i.e., before magnification and panning) of the current innermost SVG document fragment can be either the "standard" view, i.e., based on attributes on the [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element such as `viewBox`) or on a "custom" view (i.e., a hyperlink into a particular [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view) or other element). If the initial view is the "standard" view, then this attribute is `false`. If the initial view is a "custom" view, then this attribute is `true`.

<span class="page-not-created">`SVGSVGElement.currentView`</span>  
An <span class="page-not-created">`SVGViewSpec`</span> defining the initial view (i.e., before magnification and panning) of the current innermost SVG document fragment. The meaning depends on the situation: If the initial view was a "standard" view, then:

-   the values for `viewBox`, `preserveAspectRatio` and `zoomAndPan` within `currentView` will match the values for the corresponding DOM attributes that are on `SVGSVGElement` directly
-   the values for `transform` and `viewTarget` within `currentView` will be `null`

If the initial view was a link into a [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view) element, then:

-   the values for `viewBox`, `preserveAspectRatio` and `zoomAndPan` within `currentView` will correspond to the corresponding attributes for the given [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view) element
-   the values for `transform` and `viewTarget` within `currentView` will be `null`

If the initial view was a link into another element (i.e., other than a [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view)), then:

-   the values for `viewBox`, `preserveAspectRatio` and `zoomAndPan` within `currentView` will match the values for the corresponding DOM attributes that are on `SVGSVGElement` directly for the closest ancestor [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element
-   the values for `transform` within `currentView` will be `null`
-   the `viewTarget` within `currentView` will represent the target of the link

If the initial view was a link into the SVG document fragment using an SVG view specification fragment identifier (i.e., `#svgView(…)`), then:

-   the values for `viewBox`, `preserveAspectRatio`, `zoomAndPan`, `transform` and `viewTarget` within `currentView` will correspond to the values from the SVG view specification fragment identifier

<span class="page-not-created">`SVGSVGElement.currentScale`</span>  
On an outermost [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element, this float attribute indicates the current scale factor relative to the initial view to take into account user magnification and panning operations. DOM attributes `currentScale` and `currentTranslate` are equivalent to the 2×3 matrix `[a b c d e f] = [currentScale 0 0 currentScale currentTranslate.x currentTranslate.y]`. If "magnification" is enabled (i.e., `zoomAndPan="magnify"`), then the effect is as if an extra transformation were placed at the outermost level on the SVG document fragment (i.e., outside the outermost [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element).

 <span class="page-not-created">`SVGSVGElement.currentTranslate`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGPoint`](svgpoint) representing the translation factor that takes into account user "magnification" corresponding to an outermost [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element. The behavior is undefined for `<svg>` elements that are not at the outermost level.

Methods
-------

*This interface also inherits methods from its parent, [`SVGGraphicsElement`](svggraphicselement) and also implements the ones from [`SVGZoomAndPan`](svgzoomandpan), <span class="page-not-created">`SVGFitToViewBox`</span>, and [`WindowEventHandlers`](windoweventhandlers).*

 <span class="page-not-created">`SVGSVGElement.suspendRedraw()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Takes a time-out value which indicates that redraw shall not occur until:

the corresponding `unsuspendRedraw()` call has been made, an `unsuspendRedrawAll()` call has been made, or its timer has timed out.

In environments that do not support interactivity (e.g., print media), then redraw shall not be suspended. Calls to `suspendRedraw()` and `unsuspendRedraw()` should, but need not be, made in balanced pairs.

To suspend redraw actions as a collection of SVG DOM changes occur, precede the changes to the SVG DOM with a method call similar to:

    const suspendHandleID = suspendRedraw(maxWaitMilliseconds)

and follow the changes with a method call similar to:

    unsuspendRedraw(suspendHandleID)

Note that multiple `suspendRedraw()` calls can be used at once, and that each such method call is treated independently of the other `suspendRedraw()` method calls.

 <span class="page-not-created">`SVGSVGElement.unsuspendRedraw()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Cancels a specified `suspendRedraw()` by providing a unique suspend handle ID that was returned by a previous `suspendRedraw()` call.

 <span class="page-not-created">`SVGSVGElement.unsuspendRedrawAll()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Cancels all currently active `suspendRedraw()` method calls. This method is most useful at the very end of a set of SVG DOM calls to ensure that all pending `suspendRedraw()` method calls have been cancelled.

 <span class="page-not-created">`SVGSVGElement.forceRedraw()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
In rendering environments supporting interactivity, forces the user agent to immediately redraw all regions of the viewport that require updating.

<span class="page-not-created">`SVGSVGElement.pauseAnimations()`</span>  
Suspends (i.e., pauses) all currently running animations that are defined within the SVG document fragment corresponding to this [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element, causing the animation clock corresponding to this document fragment to stand still until it is unpaused.

<span class="page-not-created">`SVGSVGElement.unpauseAnimations()`</span>  
Unsuspends (i.e., unpauses) currently running animations that are defined within the SVG document fragment, causing the animation clock to continue from the time at which it was suspended.

<span class="page-not-created">`SVGSVGElement.animationsPaused()`</span>  
Returns `true` if this SVG document fragment is in a paused state.

<span class="page-not-created">`SVGSVGElement.getCurrentTime()`</span>  
Returns the current time in seconds relative to the start time for the current SVG document fragment. If `getCurrentTime()` is called before the document timeline has begun (for example, by script running in a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/script) element before the document's `SVGLoad` event is dispatched), then `0` is returned.

<span class="page-not-created">`SVGSVGElement.setCurrentTime()`</span>  
Adjusts the clock for this SVG document fragment, establishing a new current time. If `setCurrentTime()` is called before the document timeline has begun (for example, by script running in a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/script) element before the document's `SVGLoad` event is dispatched), then the value of seconds in the last invocation of the method gives the time that the document will seek to once the document timeline has begun.

<span class="page-not-created">`SVGSVGElement.getIntersectionList()`</span>  
Returns a [`NodeList`](nodelist) of graphics elements whose rendered content intersects the supplied rectangle. Each candidate graphics element is to be considered a match only if the same graphics element can be a target of pointer events as defined in `pointer-events` processing.

<span class="page-not-created">`SVGSVGElement.getEnclosureList()`</span>  
Returns a [`NodeList`](nodelist) of graphics elements whose rendered content is entirely contained within the supplied rectangle. Each candidate graphics element is to be considered a match only if the same graphics element can be a target of pointer events as defined in `pointer-events` processing.

<span class="page-not-created">`SVGSVGElement.checkIntersection()`</span>  
Returns `true` if the rendered content of the given element intersects the supplied rectangle. Each candidate graphics element is to be considered a match only if the same graphics element can be a target of pointer events as defined in `pointer-events` processing.

<span class="page-not-created">`SVGSVGElement.checkEnclosure()`</span>  
Returns `true` if the rendered content of the given element is entirely contained within the supplied rectangle. Each candidate graphics element is to be considered a match only if the same graphics element can be a target of pointer events as defined in `pointer-events` processing.

<span class="page-not-created">`SVGSVGElement.deselectAll()`</span>  
Unselects any selected objects, including any selections of text strings and type-in bars.

<span class="page-not-created">`SVGSVGElement.createSVGNumber()`</span>  
Creates an [`SVGNumber`](svgnumber) object outside of any document trees. The object is initialized to `0`.

<span class="page-not-created">`SVGSVGElement.createSVGLength()`</span>  
Creates an [`SVGLength`](svglength) object outside of any document trees. The object is initialized to `0` user units.

<span class="page-not-created">`SVGSVGElement.createSVGAngle()`</span>  
Creates an [`SVGAngle`](svgangle) object outside of any document trees. The object is initialized to a value of `0` degrees (unitless).

<span class="page-not-created">`SVGSVGElement.createSVGPoint()`</span>  
Creates an [`SVGPoint`](svgpoint) object outside of any document trees. The object is initialized to the point `(0,0)` in the user coordinate system.

<span class="page-not-created">`SVGSVGElement.createSVGMatrix()`</span>  
Creates an [`SVGMatrix`](svgmatrix) object outside of any document trees. The object is initialized to the identity matrix.

<span class="page-not-created">`SVGSVGElement.createSVGRect()`</span>  
Creates an [`SVGRect`](svgrect) object outside of any document trees. The object is initialized such that all values are set to `0` user units.

<span class="page-not-created">`SVGSVGElement.createSVGTransform()`</span>  
Creates an [`SVGTransform`](svgtransform) object outside of any document trees. The object is initialized to an identity matrix transform (`SVG_TRANSFORM_MATRIX`).

<span class="page-not-created">`SVGSVGElement.createSVGTransformFromMatrix()`</span>  
Creates an [`SVGTransform`](svgtransform) object outside of any document trees. The object is initialized to the given matrix transform (i.e., `SVG_TRANSFORM_MATRIX`). The values from the parameter matrix are copied, the matrix parameter is not adopted as `SVGTransform::matrix`.

<span class="page-not-created">`SVGSVGElement.getElementById()`</span>  
Searches this SVG document fragment (i.e., the search is restricted to a subset of the document tree) for an Element whose `id` is given by `elementId`. If an Element is found, that Element is returned. If no such element exists, returns `null`. Behavior is not defined if more than one element has this id.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/struct.html#InterfaceSVGSVGElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGSVGElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaced the inheritance from <a href="svgelement"><code>SVGElement</code></a> by <a href="svggraphicselement"><code>SVGGraphicsElement</code></a>, removed the implemented interfaces <a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, <span class="page-not-created"><code>SVGLocatable</code></span>, <span class="page-not-created"><code>DocumentEvent</code></span>, <span class="page-not-created"><code>ViewCSS</code></span>, and <span class="page-not-created"><code>DocumentCSS</code></span> and added implemented interface <a href="windoweventhandlers"><code>WindowEventHandlers</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/struct.html#InterfaceSVGSVGElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGSVGElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGSVGElement`

1

12

1.5

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`animationsPaused`

1

?

1.5

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`checkEnclosure`

1

12

1.5-21

9

≤12.1

3

1

18

4-21

≤12.1

1

1.0

`checkIntersection`

1

12

1.5-21

9

≤12.1

3

1

18

4-21

≤12.1

1

1.0

`contentScriptType`

1-36

12

1.5-20

9

≤12.1-23

3-13.1

1-37

18-36

4-20

≤12.1-24

1-13.4

1.0-3.0

`contentStyleType`

1-36

12

1.5-20

9

≤12.1-23

3-13.1

1-37

18-36

4-20

≤12.1-24

1-13.4

1.0-3.0

`createSVGAngle`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGLength`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGMatrix`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGNumber`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGPoint`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGRect`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGTransform`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`createSVGTransformFromMatrix`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`currentScale`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`currentTranslate`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`currentView`

21-56

No

1.5-21

No

15-43

6.1

≤37-56

25-56

4-21

14-43

7

1.5-6.0

`deselectAll`

1

12

25

9

≤12.1

3

1

18

25

≤12.1

1

1.0

`forceRedraw`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getCurrentTime`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getElementById`

6

12

11

9

≤12.1

5.1

≤37

18

Yes

≤12.1

5

1.0

`getEnclosureList`

1

12

No

9

≤12.1

3

1

18

No

≤12.1

1

1.0

`getIntersectionList`

1

12

No

9

≤12.1

3

1

18

No

≤12.1

1

1.0

`height`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`pauseAnimations`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`pixelUnitToMillimeterX`

1-47

12-79

1.5-61

9

≤12.1-34

3-13.1

1-47

18-47

4-61

≤12.1-34

1-13.4

1.0-5.0

`pixelUnitToMillimeterY`

1-47

12-79

1.5-61

9

≤12.1-34

3-13.1

1-47

18-47

4-61

≤12.1-34

1-13.4

1.0-5.0

`screenPixelToMillimeterX`

1-47

12-79

1.5-61

9

≤12.1-34

3-13.1

1-47

18-47

4-61

≤12.1-34

1-13.4

1.0-5.0

`screenPixelToMillimeterY`

1-47

12-79

1.5-61

9

≤12.1-34

3-13.1

1-47

18-47

4-61

≤12.1-34

1-13.4

1.0-5.0

`setCurrentTime`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`suspendRedraw`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`unpauseAnimations`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`unsuspendRedraw`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`unsuspendRedrawAll`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`useCurrentView`

1-56

No

15

No

≤12.1-43

3

1-56

18-56

15

≤12.1-43

1

1.0-6.0

`viewport`

1-55

12

1.5-21

9

≤12.1-42

3-13.1

1-55

18-55

4-21

≤12.1-42

1-13.4

1.0-6.0

`width`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`x`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`y`

1

12

1.5

9

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

-   [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGSVGElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGSVGElement</a>
