# MSGestureEvent

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `MSGestureEvent` is a proprietary interface specific to Internet Explorer and Microsoft Edge which represents events that occur due to touch gestures. Events using this interface include `MSGestureStart`, `MSGestureEnd`, `MSGestureTap`, `MSGestureHold`, `MSGestureChange`, and `MSInertiaStart`.

`MSGestureEvent` derives from [`UIEvent`](uievent), which in turn derives from [`Event`](event). Though the <span class="page-not-created">`MSGestureEvent.initGestureEvent()`</span> method is kept for backward compatibility, the creation of an `MSGestureEvent` object should be done using the <span class="page-not-created">`MSGestureEvent()`</span> constructor.

## Constructor

<span class="page-not-created">`MSGestureEvent()`</span>  
Creates an `MSGestureEvent` object.

## Properties

_This interface also inherits properties of its parents, [`UIEvent`](uievent) and [`Event`](event)._

<span class="page-not-created">`MSGestureEvent.expansion`</span> <span class="badge inline readonly">Read only </span>  
The diameter of the gesture area. For example, the distance between fingers.

<span class="page-not-created">`MSGestureEvent.gestureObject`</span> <span class="badge inline readonly">Read only </span>  
Returns the <span class="page-not-created">`MSGesture`</span> object for this gesture event.

<span class="page-not-created">`MSGestureEvent.rotation`</span> <span class="badge inline readonly">Read only </span>  
Amount of rotation (in radians) since the previous [`MSGestureEvent`](msgestureevent) of the current gesture. Positive values indicate clockwise rotation; negative values indicate counterclockwise rotation.

<span class="page-not-created">`MSGestureEvent.scale`</span> <span class="badge inline readonly">Read only </span>  
The difference in scale (for zoom gestures) from the previous [`MSGestureEvent`](msgestureevent) of the current gesture.

<span class="page-not-created">`MSGestureEvent.translationX`</span> <span class="badge inline readonly">Read only </span>  
Distance traversed along the X-axis since the previous [`MSGestureEvent`](msgestureevent) of the current gesture

<span class="page-not-created">`MSGestureEvent.translationY`</span> <span class="badge inline readonly">Read only </span>  
Distance traversed along the Y-axis since the previous [`MSGestureEvent`](msgestureevent) of the current gesture

<span class="page-not-created">`MSGestureEvent.velocityAngular`</span> <span class="badge inline readonly">Read only </span>  
Angular velocity. Expressed in radians.

<span class="page-not-created">`MSGestureEvent.velocityExpansion`</span> <span class="badge inline readonly">Read only </span>  
The velocity of the expansion of the gesture area.

<span class="page-not-created">`MSGestureEvent.velocityX`</span> <span class="badge inline readonly">Read only </span>  
Velocity along the direction of the X-axis.

<span class="page-not-created">`MSGestureEvent.velocityY`</span> <span class="badge inline readonly">Read only </span>  
Velocity along the direction of the Y-axis.

## Methods

_This interface also inherits methods of its parents, [`UIEvent`](uievent) and [`Event`](event)._

<span class="page-not-created">`MSGestureEvent.initGestureEvent()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes the value of an `MSGestureEvent`. If the event has already being dispatched, this method does nothing. This method is deprecated as of Microsoft Edge.

## Gesture event types

- `MSGestureStart`
- `MSGestureEnd`
- `MSGestureTap`
- `MSGestureHold`
- `MSGestureChange`
- `MSInertiaStart`

## Specifications

_Not part of any specification._ Microsoft has [a description on MSDN](<https://msdn.microsoft.com/en-us/library/hh772076(v=vs.85).aspx>).

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

`MSGestureEvent`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSGestureEvent`

No

12-79

No

10

No

No

No

No

No

No

No

No

`expansion`

No

12-79

No

10

No

No

No

No

No

No

No

No

`gestureObject`

No

12-79

No

10

No

No

No

No

No

No

No

No

`initGestureEvent`

No

12-79

No

10

No

No

No

No

No

No

No

No

`rotation`

No

12-79

No

10

No

No

No

No

No

No

No

No

`scale`

No

12-79

No

10

No

No

No

No

No

No

No

No

`translationX`

No

12-79

No

10

No

No

No

No

No

No

No

No

`translationY`

No

12-79

No

10

No

No

No

No

No

No

No

No

`velocityAngular`

No

12-79

No

10

No

No

No

No

No

No

No

No

`velocityExpansion`

No

12-79

No

10

No

No

No

No

No

No

No

No

`velocityX`

No

12-79

No

10

No

No

No

No

No

No

No

No

`velocityY`

No

12-79

No

10

No

No

No

No

No

No

No

No

## See also

- WebKit equivalents:
  - [`GestureEvent`](gestureevent)
  - `gesturestart`
  - `gesturechange`
  - `gestureend`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSGestureEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSGestureEvent</a>
