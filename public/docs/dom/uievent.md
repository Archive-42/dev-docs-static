UIEvent
=======

The `UIEvent` interface represents simple user interface events.

`UIEvent` derives from [`Event`](event). Although the [`UIEvent.initUIEvent()`](uievent/inituievent) method is kept for backward compatibility, you should create a `UIEvent` object using the [`UIEvent()`](uievent/uievent) constructor.

Several interfaces are direct or indirect descendants of this one: [`MouseEvent`](mouseevent), [`TouchEvent`](touchevent), [`FocusEvent`](focusevent), [`KeyboardEvent`](keyboardevent), [`WheelEvent`](wheelevent), [`InputEvent`](inputevent), and [`CompositionEvent`](compositionevent).

Constructors
------------

[`UIEvent()`](uievent/uievent)  
Creates a `UIEvent` object.

Properties
----------

*This interface also inherits properties of its parent, [`Event`](event).*

 [`UIEvent.cancelBubble`](uievent/cancelbubble) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the bubbling of the event has been canceled or not.

 [`UIEvent.detail`](uievent/detail)<span class="badge inline readonly">Read only </span>   
Returns a `long` with details about the event, depending on the event type.

 [`UIEvent.isChar`](uievent/ischar) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event produced a key character or not.

 [`UIEvent.layerX`](uievent/layerx) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the horizontal coordinate of the event relative to the current layer.

 [`UIEvent.layerY`](uievent/layery) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the vertical coordinate of the event relative to the current layer.

 [`UIEvent.pageX`](uievent/pagex) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the horizontal coordinate of the event relative to the whole document.

 [`UIEvent.pageY`](uievent/pagey) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the vertical coordinate of the event relative to the whole document.

 [`UIEvent.sourceCapabilities`](uievent/sourcecapabilities) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Returns an instance of the `InputDeviceCapabilities` interface, which provides information about the physical device responsible for generating a touch event.

 [`UIEvent.view`](uievent/view)<span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`WindowProxy`</span> that contains the view that generated the event.

 <span class="page-not-created">`UIEvent.which`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the numeric `keyCode` of the key pressed, or the character code (`charCode`) for an alphanumeric key pressed.

Methods
-------

*This interface also inherits methods of its parent, [`Event`](event).*

 [`UIEvent.initUIEvent()`](uievent/inituievent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Initializes a `UIEvent` object. If the event has already being dispatched, this method does nothing.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/">InputDeviceCapabilities</a></td><td><span class="spec-draft">Draft</span></td><td>Added <code>sourceCapabilities</code> property.</td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td><td>Extend DOM3</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-UIEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>UIEvent()</code> constructor, deprecated the <code>initUIEvent()</code> method and changed the type of <code>view</code> from <code>AbstractView</code> to <code>WindowProxy</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-UIEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`UIEvent`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`UIEvent`

Yes

≤18

11

?

Yes

Yes

Yes

Yes

14

Yes

Yes

Yes

`detail`

Yes

12

Yes

9

Always `0` on `click` and `dblclick` events. On `mousedown` and `mouseup` events, the count is not unique to the element, but is rather the global click count for the current document -- even across refreshes.

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`initUIEvent`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`isChar`

No

No

Yes-55

The `isChar` property has never been supported by any browser but Firefox, and even on Firefox it's never worked except on Mac OSX. For that reason, it's been removed in Firefox 55 to align with other browsers.

No

No

No

No

No

Yes-55

The `isChar` property has never been supported by any browser but Firefox, and even on Firefox it's never worked except on Mac OSX. For that reason, it's been removed in Firefox 55 to align with other browsers.

No

No

No

`layerX`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`layerY`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`pageX`

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

12

?

9

?

Yes

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

?

?

Yes

Yes-4.0

Replaced by `MouseEvent.pageX` in Samsung Internet 5.0.

`pageY`

Yes-44

Replaced by `MouseEvent.pageY` in version 45.

12

?

9

?

Yes

Yes-44

Replaced by `MouseEvent.pageY` in version 45.

Yes-44

Replaced by `MouseEvent.pageY` in version 45.

?

?

Yes

Yes-4.0

Replaced by `MouseEvent.pageY` in Samsung Internet 5.0.

`sourceCapabilities`

47

≤79

?

No

Yes

No

47

47

?

Yes

No

5.0

`view`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`which`

Yes

≤79

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   [`Event`](event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent</a>
