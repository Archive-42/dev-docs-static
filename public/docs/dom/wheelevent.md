WheelEvent
==========

The `WheelEvent` interface represents events that occur due to the user moving a mouse wheel or similar input device.

**Important: This is the standard wheel event interface to use.** Old versions of browsers implemented the non-standard and non-cross-browser-compatible [`MouseWheelEvent`](mousewheelevent) and [`MouseScrollEvent`](mousescrollevent) interfaces. Use this interface and avoid the non-standard ones.

**Do not confuse the [`wheel`](element/wheel_event) event with the [`scroll`](element/scroll_event) event:** The default action of a `wheel` event is implementation-defined. Thus, a `wheel` event doesn't necessarily dispatch a `scroll` event. Even when it does, that doesn't mean that the `delta*` values in the `wheel` event necessarily reflect the content's scrolling direction. Therefore, do not rely on `delta*` properties to get the content's scrolling direction. Instead, detect value changes to [`scrollLeft`](element/scrollleft) and [`scrollTop`](element/scrolltop) of the target in the `scroll` event.

Constructor
-----------

[`WheelEvent()`](wheelevent/wheelevent)  
Creates a `WheelEvent` object.

Properties
----------

*This interface inherits properties from its ancestors, [`MouseEvent`](mouseevent), [`UIEvent`](uievent), and [`Event`](event).*

 [`WheelEvent.deltaX`](wheelevent/deltax)<span class="badge inline readonly">Read only </span>   
Returns a `double` representing the horizontal scroll amount.

 [`WheelEvent.deltaY`](wheelevent/deltay)<span class="badge inline readonly">Read only </span>   
Returns a `double` representing the vertical scroll amount.

 [`WheelEvent.deltaZ`](wheelevent/deltaz)<span class="badge inline readonly">Read only </span>   
Returns a `double` representing the scroll amount for the z-axis.

 [`WheelEvent.deltaMode`](wheelevent/deltamode)<span class="badge inline readonly">Read only </span>   
Returns an `unsigned long` representing the unit of the `delta*` values' scroll amount. Permitted values are:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>WheelEvent.DOM_DELTA_PIXEL</code></td><td><code>0x00</code></td><td>The <code>delta*</code> values are specified in pixels.</td></tr><tr class="even"><td><code>WheelEvent.DOM_DELTA_LINE</code></td><td><code>0x01</code></td><td>The <code>delta*</code> values are specified in lines.</td></tr><tr class="odd"><td><code>WheelEvent.DOM_DELTA_PAGE</code></td><td><code>0x02</code></td><td>The <code>delta*</code> values are specified in pages.</td></tr></tbody></table>

Methods
-------

*This interface doesn't define any specific methods, but inherits methods from its ancestors, [`MouseEvent`](mouseevent), [`UIEvent`](uievent), and [`Event`](event).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#interface-wheelevent">UI Events<br />
<span class="small">The definition of 'The <code>WheelEvent</code> interface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-wheelevent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WheelEvent`

31

12

17

9

18

6.1

≤37

Yes

17

Yes

No

Yes

`WheelEvent`

Yes

≤18

17

No

Yes

6.1

Yes

Yes

17

Yes

No

Yes

`deltaMode`

31

12

17

9

18

6.1

≤37

Yes

17

Yes

No

Yes

`deltaX`

31

12

17

9

IE9 supports an old draft of the spec where this value was a `long` instead of a `double`.

18

6.1

≤37

Yes

17

Yes

No

Yes

`deltaY`

31

12

17

9

IE9 supports an old draft of the spec where this value was a `long` instead of a `double`.

18

6.1

≤37

Yes

17

Yes

No

Yes

`deltaZ`

31

12

17

9

IE9 supports an old draft of the spec where this value was a `long` instead of a `double`.

18

6.1

≤37

Yes

17

Yes

No

Yes

`pinch-to-zoom_support`

31

≤79

55

?

?

No

≤37

Yes

55

?

No

Yes

See also
--------

-   [`wheel`](element/wheel_event) event
-   Interfaces replaced by this one:
    -   Gecko's legacy mouse wheel event object: [`MouseScrollEvent`](mousescrollevent)
    -   Non-gecko browsers' legacy mouse wheel event object: [`MouseWheelEvent`](mousewheelevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent</a>
