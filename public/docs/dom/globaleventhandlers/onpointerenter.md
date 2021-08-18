GlobalEventHandlers.onpointerenter
==================================

The `onpointerenter` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes [`pointerenter`](../htmlelement/pointerenter_event) events.

Syntax
------

    targetElement.onpointerenter = enterHandler;

    var enterHandler = targetElement.onpointerenter;

### Value

`enterHandler`  
The `pointerenter` event handler for element `targetElement`.

Example
-------

This example shows two ways to use `onpointerenter` to set an element's `pointerenter` event handler.

    <html>
    <script>
    function enterHandler(ev) {
      // Process the pointerenter event
    }
    function init() {
      let el = document.getElementById('target1');
      el.onpointerenter = enterHandler;
    }
    </script>

    <body onload="init();">
      <div id="target1"> Touch me ... </div>
      <div id="target2" onpointerenter="enterHandler(event)"> Touch me ... </div>
    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-globaleventhandlers-onpointerenter">Pointer Events – Level 2<br />
<span class="small">The definition of 'onpointerenter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-GlobalEventHandlers-onpointerenter">Pointer Events<br />
<span class="small">The definition of 'onpointerenter' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`onpointerenter`

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

-   `Document: pointerenter` event
-   `HTMLElement: pointerenter` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerenter</a>
