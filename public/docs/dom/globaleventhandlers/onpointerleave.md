GlobalEventHandlers.onpointerleave
==================================

The [global event handler](../globaleventhandlers) for the [`pointerleave`](../htmlelement/pointerleave_event) event, which is delivered to a [`Node`](../node) when the pointer (mouse cursor, fingertip, etc.) exits its hit test area (for example, if the cursor exits an [`Element`](../element) or [`Window`](../window)'s content area). This event is part of the [Pointer Events API](../pointer_events).

Syntax
------

    EventTarget.onpointerleave = leaveHandler;

    var leaveHandler = EventTarget.onpointerleave;

### Value

`leaveHandler`  
The [`EventListener`](../eventlistener) which will be invoked to handle [`pointerleave`](../htmlelement/pointerleave_event) events sent to the target.

Example
-------

This example shows two ways to use `onpointerleave` to set an element's `pointerleave` event handler.

    <html>
    <script>
    function leaveHandler(ev) {
     // Process the pointerleave event
    }
    function init() {
     var el=document.getElementById("target1");
     el.onpointerleave = leaveHandler;
    }
    </script>
    <body onload="init();">
    <div id="target1"> Touch me ... </div>
    <div id="target2" onpointerleave="leaveHandler(event)"> Touch me ... </div>
    </body>
    </html>

See [Using Pointer Events](../pointer_events/using_pointer_events) for additional details.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-globaleventhandlers-onpointerleave">Pointer Events – Level 2<br />
<span class="small">The definition of 'onpointerleave' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-GlobalEventHandlers-onpointerleave">Pointer Events<br />
<span class="small">The definition of 'onpointerleave' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`onpointerleave`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

See also
--------

-   [Pointer events](../pointer_events)
-   [Using pointer events](../pointer_events/using_pointer_events)
-   `Document: pointerleave` event
-   `HTMLElement: pointerleave` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerleave</a>
