SVGAnimationElement
===================

The `SVGAnimationElement` interface is the base interface for all of the animation element interfaces: [`SVGAnimateElement`](svganimateelement), [`SVGSetElement`](svgsetelement), [`SVGAnimateColorElement`](svganimatecolorelement), [`SVGAnimateMotionElement`](svganimatemotionelement) and [`SVGAnimateTransformElement`](svganimatetransformelement).

Properties
----------

*This interface also inherits properties from its parent, [`SVGElement`](svgelement).*

 [`SVGAnimationElement.targetElement`](svganimationelement/targetelement) <span class="badge inline readonly">Read only </span>   
An [`SVGElement`](svgelement) representing the element which is being animated. If no target element is being animated (for example, because the `href` specifies an unknown element) the value returned is `null`.

Methods
-------

*This interface also inherits methods from its parent, [`SVGElement`](svgelement).*

<span class="page-not-created">`SVGAnimationElement.getStartTime()`</span>  
Returns a float representing the begin time, in seconds, for this animation element's current interval, if it exists, regardless of whether the interval has begun yet. If there is no current interval, then a [`DOMException`](domexception) with code `INVALID_STATE_ERR` is thrown.

<span class="page-not-created">`SVGAnimationElement.getCurrentTime()`</span>  
Returns a float representing the current time in seconds relative to time zero for the given time container.

<span class="page-not-created">`SVGAnimationElement.getSimpleDuration()`</span>  
Returns a float representing the number of seconds for the simple duration for this animation. If the simple duration is undefined (e.g., the end time is indefinite), then a [`DOMException`](domexception) with code `NOT_SUPPORTED_ERR` is raised.

 <span class="page-not-created">`SVGAnimationElement.beginElement()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates a begin instance time for the current time. The new instance time is added to the begin instance times list. The behavior of this method is equivalent to `beginElementAt(0)`.

 <span class="page-not-created">`SVGAnimationElement.beginElementAt()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates a begin instance time for the current time plus the specified offset. The new instance time is added to the begin instance times list.

 <span class="page-not-created">`SVGAnimationElement.endElement()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates an end instance time for the current time. The new instance time is added to the end instance times list. The behavior of this method is equivalent to `endElementAt(0)`.

 <span class="page-not-created">`SVGAnimationElement.endElementAt()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates a end instance time for the current time plus the specified offset. The new instance time is added to the end instance times list.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `on...` handler property of this interface.

`beginEvent`  
Fired when the element local timeline begins to play.  
Also available via the `onbegin` property.

`endEvent`  
Fired when at the active end of the animation is reached.  
Also available via the `onend` property.

`repeatEvent`  
Fired when the element's local timeline repeats. It will be fired each time the element repeats, after the first iteration.  
Also available via the `onrepeat` property.

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://svgwg.org/specs/animations/#InterfaceSVGAnimationElement">SVG Animations Level 2<br />
<span class="small">The definition of 'SVGAnimationElement' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/animate.html#InterfaceSVGAnimationElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGAnimationElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGAnimationElement`

1

79

4

No

≤12.1

1

1

18

4

≤12.1

1

1.0

`beginElement`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`beginElementAt`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`beginEvent_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

?

?

?

Yes

`endElement`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`endElementAt`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`endEvent_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

?

?

?

Yes

`getCurrentTime`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`getSimpleDuration`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`getStartTime`

1

79

4

No

15

4

1

18

4

14

3.2

1.0

`onbegin`

35

79

Yes

No

22

No

37

35

?

22

No

3.0

`onend`

35

79

Yes

No

22

No

37

35

?

22

No

3.0

`onrepeat`

35

79

Yes

No

22

No

37

35

?

22

No

3.0

`repeatEvent_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

?

?

?

Yes

`targetElement`

1

79

4

No

≤12.1

4

1

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement</a>
