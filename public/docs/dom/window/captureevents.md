Window.captureEvents()
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.captureEvents()` method registers the window to capture all events of the specified type.

Syntax
------

    window.captureEvents(eventType)

`eventType` is a combination of the following values: `Event.ABORT`, `Event.BLUR`, `Event.CLICK`, `Event.CHANGE`, `Event.DBLCLICK`, `Event.DRAGDDROP`, `Event.ERROR`, `Event.FOCUS`, `Event.KEYDOWN`, `Event.KEYPRESS`, `Event.KEYUP`, `Event.LOAD`, `Event.MOUSEDOWN`, `Event.MOUSEMOVE`, `Event.MOUSEOUT`, `Event.MOUSEOVER`, `Event.MOUSEUP`, `Event.MOVE`, `Event.RESET`, `Event.RESIZE`, `Event.SELECT`, `Event.SUBMIT`, `Event.UNLOAD`.

Example
-------

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <!-- ... -->
    <script>
    function reg() {
      window.captureEvents(Event.CLICK);
      window.onclick = page_click;
    }

    function page_click() {
      alert('page click event detected!');
    }
    </script>
    </head>

    <body onload="reg();">
    <p>click anywhere on this page.</p>
    </body>
    </html>

Notes
-----

Events raised in the DOM by user activity (such as clicking buttons or shifting focus away from the current document) generally pass through the high-level [`window`](../window) and [`document`](../document) objects first before arriving at the object that initiated the event.

When you call the `captureEvents()` method on the [`window`](../window), events of the type you specify (for example, `Event.CLICK`) no longer pass through to "lower" objects in the hierarchy. In order for events to "bubble up" in the way that they normally do, you must call [`window.releaseEvents()`](releaseevents) (<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>) on the window to keep it from trapping events.

Note that you can pass a list of events to this method using the following syntax: `window.captureEvents(Event.KEYPRESS | Event.KEYDOWN | Event.KEYUP)`.

Specifications
--------------

This is not part of any specification.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/captureEvents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/captureEvents</a>
