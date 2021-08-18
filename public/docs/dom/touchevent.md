TouchEvent
==========

The `TouchEvent` interface represents an [`UIEvent`](uievent) which is sent when the state of contacts with a touch-sensitive surface changes. This surface can be a touch screen or trackpad, for example. The event can describe one or more points of contact with the screen and includes support for detecting movement, addition and removal of contact points, and so forth.

Touches are represented by the [`Touch`](touch) object; each touch is described by a position, size and shape, amount of pressure, and target element. Lists of touches are represented by [`TouchList`](touchlist) objects.

Constructor
-----------

[`TouchEvent()`](touchevent/touchevent)  
Creates a `TouchEvent` object.

Properties
----------

*This interface inherits properties from its parent, [`UIEvent`](uievent) and [`Event`](event).*

 [`TouchEvent.altKey`](touchevent/altkey) <span class="badge inline readonly">Read only </span>   
A Boolean value indicating whether or not the alt key was down when the touch event was fired.

 [`TouchEvent.changedTouches`](touchevent/changedtouches) <span class="badge inline readonly">Read only </span>   
A [`TouchList`](touchlist) of all the [`Touch`](touch) objects representing individual points of contact whose states changed between the previous touch event and this one.

 [`TouchEvent.ctrlKey`](touchevent/ctrlkey) <span class="badge inline readonly">Read only </span>   
A Boolean value indicating whether or not the control key was down when the touch event was fired.

 [`TouchEvent.metaKey`](touchevent/metakey) <span class="badge inline readonly">Read only </span>   
A Boolean value indicating whether or not the meta key was down when the touch event was fired.

 [`TouchEvent.shiftKey`](touchevent/shiftkey) <span class="badge inline readonly">Read only </span>   
A Boolean value indicating whether or not the shift key was down when the touch event was fired.

 [`TouchEvent.targetTouches`](touchevent/targettouches)<span class="badge inline readonly">Read only </span>   
A [`TouchList`](touchlist) of all the [`Touch`](touch) objects that are both currently in contact with the touch surface **and** were also started on the same element that is the target of the event.

 [`TouchEvent.touches`](touchevent/touches) <span class="badge inline readonly">Read only </span>   
A [`TouchList`](touchlist) of all the [`Touch`](touch) objects representing all current points of contact with the surface, regardless of target or changed status.

 <span class="page-not-created">`TouchEvent.rotation`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Change in rotation (in degrees) since the event's beginning. Positive values indicate clockwise rotation; negative values indicate counterclockwise rotation. Initial value: `0.0`

 <span class="page-not-created">`TouchEvent.scale`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Distance between two digits since the event's beginning. Expressed as a floating-point multiple of the initial distance between the digits at the beginning of the event. Values below 1.0 indicate an inward pinch (zoom out). Values above 1.0 indicate an outward unpinch (zoom in). Initial value: `1.0`

Touch event types
-----------------

There are several types of event that can be fired to indicate that touch-related changes have occurred. You can determine which of these has happened by looking at the event's [`TouchEvent.type`](event/type) property.

### `touchstart`

Sent when the user places a touch point on the touch surface. The event's target will be the [`element`](element) in which the touch occurred.

### `touchend`

Sent when the user removes a touch point from the surface (that is, when they lift a finger or stylus from the surface). This is also sent if the touch point moves off the edge of the surface; for example, if the user's finger slides off the edge of the screen.

The event's target is the same [`element`](element) that received the `touchstart` event corresponding to the touch point, even if the touch point has moved outside that element.

The touch point (or points) that were removed from the surface can be found in the [`TouchList`](touchlist) specified by the `changedTouches` attribute.

### `touchmove`

Sent when the user moves a touch point along the surface. The event's target is the same [`element`](element) that received the `touchstart` event corresponding to the touch point, even if the touch point has moved outside that element.

This event is also sent if the values of the radius, rotation angle, or force attributes of a touch point change.

**Note:** The rate at which `touchmove` events is sent is browser-specific, and may also vary depending on the capability of the user's hardware. You must not rely on a specific granularity of these events.

### `touchcancel`

Sent when a touch point has been disrupted in some way. There are several possible reasons why this might happen (and the exact reasons will vary from device to device, as well as browser to browser):

-   An event of some kind occurred that canceled the touch; this might happen if a modal alert pops up during the interaction.
-   The touch point has left the document window and moved into the browser's UI area, a plug-in, or other external content.
-   The user has placed more touch points on the screen than can be supported, in which case the earliest [`Touch`](touch) in the [`TouchList`](touchlist) gets canceled.

### Using with addEventListener() and preventDefault()

It's important to note that in many cases, both touch and mouse events get sent (in order to let non-touch-specific code still interact with the user). If you use touch events, you should call [`preventDefault()`](event/preventdefault) to keep the mouse event from being sent as well.

The exception to this is Chrome, starting with version 56 (desktop, Chrome for android, and android webview), where the default value for the `passive` option for [`touchstart`](element/touchstart_event) and [`touchmove`](element/touchmove_event) is `true` and calls to [`preventDefault()`](event/preventdefault) will have no effect. To override this behavior, you need to set the `passive` option to `false`, after which calling [`preventDefault()`](event/preventdefault) will work as specified. The change to treat listeners as `passive` by default prevents the listener from blocking page rendering while a user is scrolling. A demo is available on the [Google Developer](https://developers.google.com/web/updates/2016/06/passive-event-listeners) site.

GlobalEventHandlers
-------------------

The [`GlobalEventHandlers`](globaleventhandlers) mixin defines these events as global events that are available on any element in the DOM that the user can interact with.

 [`GlobalEventHandlers.ontouchstart`](globaleventhandlers/ontouchstart) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [global event handler](globaleventhandlers) for the [`touchstart`](element/touchstart_event) event.

 [`GlobalEventHandlers.ontouchend`](globaleventhandlers/ontouchend) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [global event handler](globaleventhandlers) for the [`touchend`](element/touchend_event) event.

 [`GlobalEventHandlers.ontouchmove`](globaleventhandlers/ontouchmove) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [global event handler](globaleventhandlers) for the [`touchmove`](element/touchmove_event) event.

 [`GlobalEventHandlers.ontouchcancel`](globaleventhandlers/ontouchcancel) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [global event handler](globaleventhandlers) for the [`touchcancel`](element/touchcancel_event) event.

Example
-------

See the [example on the main Touch events article](touch_events#example).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#touchevent-interface">Touch Events – Level 2<br />
<span class="small">The definition of 'TouchEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Added <code>ontouchstart</code>, <code>ontouchend</code>, <code>ontouchmove</code>, <code>ontouchend</code> global attribute handlers</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#touchevent-interface">Touch Events<br />
<span class="small">The definition of 'TouchEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TouchEvent`

22

79

≤18-79

52

18-24

Removed in [bug 888304](https://bugzil.la/888304) due to web compatibility issues.

No

15

No

≤37

25

6

14

Yes

1.5

`TouchEvent`

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

≤79

Edge only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

?

No

Yes

No

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

48

Chrome only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

Yes

Yes

3.2

5.0

Samsung Internet only supports the following `touchEventInit` properties: `touches`, `targetTouches`, `changedTouches`.

`altKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`changedTouches`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`ctrlKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`metaKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`shiftKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`targetTouches`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

`touches`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

See also
--------

-   [Touch events](touch_events)
-   [`GestureEvent`](gestureevent)
-   [`MSGestureEvent`](msgestureevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent</a>
