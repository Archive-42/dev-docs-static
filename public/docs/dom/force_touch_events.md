# Force Touch events

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Force Touch events** are a proprietary, Apple-specific feature which makes possible (where supported by the input hardware) new interactions based on how hard the user clicks or presses down on the touchscreen or trackpad.

## Events

`webkitmouseforcewillbegin` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This event is fired before the `mousedown` event. Its main use is that it can be [`Event.preventDefault()`](event/preventdefault)ed.

`webkitmouseforcedown` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This event is fired after the `mousedown` event as soon as sufficient pressure has been applied for it to qualify as a "force click".

`webkitmouseforceup` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This event is fired after the `webkitmouseforcedown` event as soon as the pressure has been reduced sufficiently to end the "force click".

`webkitmouseforcechanged` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This event is fired each time the amount of pressure changes. This event first fires after the `mousedown` event and stops firing before the `mouseup` event.

## Event properties

The following property is known to be available on the `webkitmouseforcewillbegin`, `mousedown`, `webkitmouseforcechanged`, `webkitmouseforcedown`, `webkitmouseforceup`, `mousemove`, and `mouseup` event objects:

[`MouseEvent.webkitForce`](mouseevent/webkitforce) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The amount of pressure currently being applied to the trackpad/touchscreen

## Constants

These constants are useful for determining the relative intensity of the pressure indicated by [`MouseEvent.webkitForce`](mouseevent/webkitforce):

[`MouseEvent.WEBKIT_FORCE_AT_MOUSE_DOWN`](mouseevent/webkit_force_at_mouse_down) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>  
Minimum force necessary for a normal click

[`MouseEvent.WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN`](mouseevent/webkit_force_at_force_mouse_down) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>  
Minimum force necessary for a force click

## Specifications

_Not part of any specification._ Apple has [a description at the Mac Developer Library](https://developer.apple.com/library/prerelease/mac/documentation/AppleApplications/Conceptual/SafariJSProgTopics/RespondingtoForceTouchEventsfromJavaScript.html).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Force_Touch_events" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Force_Touch_events</a>
