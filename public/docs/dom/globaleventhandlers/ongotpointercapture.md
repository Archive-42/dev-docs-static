GlobalEventHandlers.ongotpointercapture
=======================================

The `ongotpointercapture` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `gotpointercapture` events.

Syntax
------

    target.ongotpointercapture = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`PointerEvent`](../pointerevent) object as its sole argument.

Example
-------

    function overHandler(event) {
      // Determine the target event's gotpointercapture handler
      let gotCaptureHandler = event.target.ongotpointercapture;
    }

    function init() {
      let el = document.getElementById('target');
      el.ongotpointercapture = overHandler;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-gotpointercapture-event">Pointer Events – Level 2<br />
<span class="small">The definition of 'ongotpointercapture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`ongotpointercapture`

57

17

59

No

44

13

57

57

79

43

13

7.0

See also
--------

-   `Document: gotpointercapture` event
-   `HTMLElement: gotpointercapture` event
-   [`Element.setPointerCapture()`](../element/setpointercapture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ongotpointercapture</a>
