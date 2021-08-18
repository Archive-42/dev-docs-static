# GestureEvent

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `GestureEvent` is a proprietary interface specific to WebKit which gives information regarding multi-touch gestures. Events using this interface include `gesturestart`, `gesturechange`, and `gestureend`.

`GestureEvent` derives from [`UIEvent`](uievent), which in turn derives from [`Event`](event).

## Constructor

<span class="page-not-created">`GestureEvent()`</span>  
Creates a `GestureEvent` object.

## Properties

_This interface also inherits properties of its parents, [`UIEvent`](uievent) and [`Event`](event)._

<span class="page-not-created">`GestureEvent.rotation`</span> <span class="badge inline readonly">Read only </span>  
Change in rotation (in degrees) since the event's beginning. Positive values indicate clockwise rotation; negative values indicate counterclockwise rotation. Initial value: `0.0`

<span class="page-not-created">`GestureEvent.scale`</span> <span class="badge inline readonly">Read only </span>  
Distance between two digits since the event's beginning. Expressed as a floating-point multiple of the initial distance between the digits at the beginning of the gesture. Values below 1.0 indicate an inward pinch (zoom out). Values above 1.0 indicate an outward unpinch (zoom in). Initial value: `1.0`

## Methods

_This interface also inherits methods of its parents, [`UIEvent`](uievent) and [`Event`](event)._

<span class="page-not-created">`GestureEvent.initGestureEvent()`</span>  
Initializes the value of an `GestureEvent`. If the event has already being dispatched, this method does nothing.

## Gesture event types

- `gesturestart`
- `gesturechange`
- `gestureend`

## Specifications

_Not part of any specification._ Apple has [a description at the Safari Developer Library](https://developer.apple.com/library/iad/documentation/UserExperience/Reference/GestureEventClassReference/index.html).

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

`GestureEvent`

No

No

No

No

No

9

No

No

No

No

2

No

`GestureEvent`

No

No

No

No

No

9

No

No

No

No

2

No

`initGestureEvent`

No

No

No

No

No

9

No

No

No

No

2

No

`rotation`

No

No

No

No

No

9

No

No

No

No

2

No

`scale`

No

No

No

No

No

9

No

No

No

No

2

No

## See also

- [`MSGestureEvent`](msgestureevent)
- `MSGestureStart`
- `MSGestureEnd`
- `MSGestureTap`
- `MSGestureHold`
- `MSGestureChange`
- `MSInertiaStart`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GestureEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GestureEvent</a>
