PointerEvent
============

The `PointerEvent` interface represents the state of a DOM event produced by a pointer such as the geometry of the contact point, the device type that generated the event, the amount of pressure that was applied on the contact surface, etc.

A *pointer* is a hardware agnostic representation of input devices (such as a mouse, pen or contact point on a touch-enable surface). The pointer can target a specific coordinate (or set of coordinates) on the contact surface such as a screen.

A pointer's *hit test* is the process a browser uses to determine the target element for a pointer event. Typically, this is determined by considering the pointer's location and also the visual layout of elements in a document on screen media.

Constructors
------------

[`PointerEvent()`](pointerevent/pointerevent)  
Creates a synthetic—and untrusted—`PointerEvent`.

Properties
----------

*This interface inherits properties from [`MouseEvent`](mouseevent) and [`Event`](event).*

 [`PointerEvent.pointerId`](pointerevent/pointerid) <span class="badge inline readonly">Read only </span>   
A unique identifier for the pointer causing the event.

 [`PointerEvent.width`](pointerevent/width) <span class="badge inline readonly">Read only </span>   
The width (magnitude on the X axis), in CSS pixels, of the contact geometry of the pointer.

 [`PointerEvent.height`](pointerevent/height) <span class="badge inline readonly">Read only </span>   
The height (magnitude on the Y axis), in CSS pixels, of the contact geometry of the pointer.

 [`PointerEvent.pressure`](pointerevent/pressure) <span class="badge inline readonly">Read only </span>   
The normalized pressure of the pointer input in the range `0` to `1`, where `0` and `1` represent the minimum and maximum pressure the hardware is capable of detecting, respectively.

 [`PointerEvent.tangentialPressure`](pointerevent/tangentialpressure) <span class="badge inline readonly">Read only </span>   
The normalized tangential pressure of the pointer input (also known as barrel pressure or [cylinder stress](https://en.wikipedia.org/wiki/Cylinder_stress)) in the range `-1` to `1`, where `0` is the neutral position of the control.

 [`PointerEvent.tiltX`](pointerevent/tiltx) <span class="badge inline readonly">Read only </span>   
The plane angle (in degrees, in the range of `-90` to `90`) between the Y–Z plane and the plane containing both the pointer (e.g. pen stylus) axis and the Y axis.

 [`PointerEvent.tiltY`](pointerevent/tilty) <span class="badge inline readonly">Read only </span>   
The plane angle (in degrees, in the range of `-90` to `90`) between the X–Z plane and the plane containing both the pointer (e.g. pen stylus) axis and the X axis.

 [`PointerEvent.twist`](pointerevent/twist) <span class="badge inline readonly">Read only </span>   
The clockwise rotation of the pointer (e.g. pen stylus) around its major axis in degrees, with a value in the range `0` to `359`.

 [`PointerEvent.pointerType`](pointerevent/pointertype) <span class="badge inline readonly">Read only </span>   
Indicates the device type that caused the event (mouse, pen, touch, etc.)

 [`PointerEvent.isPrimary`](pointerevent/isprimary) <span class="badge inline readonly">Read only </span>   
Indicates if the pointer represents the primary pointer of this pointer type.

Methods
-------

 [`PointerEvent.getCoalescedEvents()`](pointerevent/getcoalescedevents) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a sequence of all `PointerEvent` instances that were coalesced into the dispatched `pointermove` event.

 <span class="page-not-created">`PointerEvent.getPredictedEvents()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a sequence of `PointerEvent` instances that the browser predicts will follow the dispatched `pointermove` event's coalesced events.

Pointer event types
-------------------

The `PointerEvent` interface has several event types. To determine which event fired, look at the event's [`type`](event/type) property.

**Note:** It's important to note that in many cases, both pointer and mouse events get sent (in order to let non-pointer-specific code still interact with the user). If you use pointer events, you should call [`event.preventDefault()`](event/preventdefault) to keep the mouse event from being sent as well.

`pointerover`  
This event is fired when a pointing device is moved into an element's hit test boundaries.

`pointerenter`  
This event is fired when a pointing device is moved into the hit test boundaries of an element or one of its descendants, including as a result of a pointerdown event from a device that does not support hover (see pointerdown). This event type is similar to `pointerover`, but differs in that it does not bubble.

`pointerdown`  
The event is fired when a pointer becomes *active*. For mouse, it is fired when the device transitions from no buttons depressed to at least one button depressed. For touch, it is fired when physical contact is made with the digitizer. For pen, it is fired when the stylus makes physical contact with the digitizer.

`pointermove`  
This event is fired when a pointer changes coordinates.

 `pointerrawupdate` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
This event is fired when any of a pointer's properties change.

`pointerup`  
This event is fired when a pointer is no longer *active*.

`pointercancel`  
A browser fires this event if it concludes the pointer will no longer be able to generate events (for example the related device is deactivated).

`pointerout`  
This event is fired for several reasons including: pointing device is moved out of the hit test boundaries of an element; firing the `pointerup` event for a device that does not support hover (see `pointerup`); after firing the `pointercancel` event (see `pointercancel`); when a pen stylus leaves the hover range detectable by the digitizer.

`pointerleave`  
This event is fired when a pointing device is moved out of the hit test boundaries of an element. For pen devices, this event is fired when the stylus leaves the hover range detectable by the digitizer.

`gotpointercapture`  
This event is fired when an element receives pointer capture.

`lostpointercapture`  
This event is fired after pointer capture is released for a pointer.

GlobalEventHandlers
-------------------

[`GlobalEventHandlers.onpointerover`](globaleventhandlers/onpointerover)  
A [`global event handler`](globaleventhandlers) for the `pointerover` event.

[`GlobalEventHandlers.onpointerenter`](globaleventhandlers/onpointerenter)  
A [`global event handler`](globaleventhandlers) for the `pointerenter` event.

[`GlobalEventHandlers.onpointerdown`](globaleventhandlers/onpointerdown)  
A [`global event handler`](globaleventhandlers) for the `pointerdown` event.

[`GlobalEventHandlers.onpointermove`](globaleventhandlers/onpointermove)  
A [`global event handler`](globaleventhandlers) for the `pointermove` event.

[`GlobalEventHandlers.onpointerup`](globaleventhandlers/onpointerup)  
A [`global event handler`](globaleventhandlers) for the `pointerup` event.

[`GlobalEventHandlers.onpointercancel`](globaleventhandlers/onpointercancel)  
A [`global event handler`](globaleventhandlers) for the `pointercancel` event.

[`GlobalEventHandlers.onpointerout`](globaleventhandlers/onpointerout)  
A [`global event handler`](globaleventhandlers) for the `pointerout` event.

[`GlobalEventHandlers.onpointerleave`](globaleventhandlers/onpointerleave)  
A [`global event handler`](globaleventhandlers) for the `pointerleave` event.

Example
-------

Examples of each property, event type, and global event handler are included in their respective reference pages.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerevents/#pointerevent-interface">Pointer Events – Level 3<br />
<span class="small">The definition of 'PointerEvent' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added the <a href="pointerevent/getcoalescedevents"><code>getCoalescedEvents()</code></a> and <span class="page-not-created"><code>getPredictedEvents()</code></span> methods and <code>pointerrawupdate</code> event.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents2/#pointerevent-interface">Pointer Events – Level 2<br />
<span class="small">The definition of 'PointerEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <a href="pointerevent/twist"><code>twist</code></a> and <a href="pointerevent/tangentialpressure"><code>tangentialPressure</code></a> properties.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents1/#pointerevent-interface">Pointer Events<br />
<span class="small">The definition of 'PointerEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PointerEvent`

55

12

59

41

11

10

See [MSDN Pointer events updates](https://msdn.microsoft.com/library/dn304886).

42

13

55

55

79

41

42

13

6.0

`PointerEvent`

55

12

59

41

11

10

See [MSDN Pointer events updates](https://msdn.microsoft.com/library/dn304886).

42

13

55

55

79

41

42

13

6.0

`getCoalescedEvents`

58

79

59

No

45

No

58

58

79

59

43

No

7.0

`height`

55

12

59

41

11

10

Returns values in screen pixels instead of CSS document pixels.

42

13

55

55

79

41

42

13

6.0

`isPrimary`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`pointerId`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`pointerType`

55

12

59

41

11

10

Returns an integer enumeration instead of a string.

42

13

55

55

79

41

42

13

6.0

`pressure`

55

12

59

41

11

10

Returns 0 instead of 0.5 on hardware that doesn't support pressure.

42

13

55

55

79

41

42

13

6.0

`tangentialPressure`

58

79

59

54

No

45

13

58

58

79

54

43

13

7.0

`tiltX`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`tiltY`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`twist`

58

18

59

54

No

45

13

58

58

79

54

43

13

7.0

`width`

55

12

59

41

11

10

Returns values in screen pixels instead of CSS document pixels.

42

13

55

55

79

41

42

13

6.0

See also
--------

-   [`Touch Events`](touch_events)
-   [`GestureEvent`](gestureevent)
-   [`MSGestureEvent`](msgestureevent)
-   [`touch-action`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent</a>
