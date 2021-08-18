Window.releaseEvents()
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Releases the window from trapping events of a specific type.

Syntax
------

    window.releaseEvents(eventType)

`eventType` is a combination of the following values: `Event.ABORT`, `Event.BLUR`, `Event.CLICK`, `Event.CHANGE`, `Event.DBLCLICK`, `Event.DRAGDDROP`, `Event.ERROR`, `Event.FOCUS`, `Event.KEYDOWN`, `Event.KEYPRESS`, `Event.KEYUP`, `Event.LOAD`, `Event.MOUSEDOWN`, `Event.MOUSEMOVE`, `Event.MOUSEOUT`, `Event.MOUSEOVER`, `Event.MOUSEUP`, `Event.MOVE`, `Event.RESET`, `Event.RESIZE`, `Event.SELECT`, `Event.SUBMIT`, `Event.UNLOAD`.

Example
-------

    window.releaseEvents(Event.KEYPRESS)

Notes
-----

Note that you can pass a list of events to this method using the following syntax: `window.releaseEvents(Event.KEYPRESS | Event.KEYDOWN | Event.KEYUP)`.

See also [`window.captureEvents`](captureevents) (<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>).

Specifications
--------------

This is not part of any specification.

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

`releaseEvents`

1

12

1

11

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/releaseEvents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/releaseEvents</a>
