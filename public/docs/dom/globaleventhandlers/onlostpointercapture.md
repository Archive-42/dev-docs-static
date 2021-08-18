# GlobalEventHandlers.onlostpointercapture

The `onlostpointercapture` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `lostpointercapture` events.

## Syntax

    target.onlostpointercapture = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`PointerEvent`](../pointerevent) object as its sole argument.

## Example

    function overHandler(event) {
      // Determine the target event's lostpointercapture handler
      let lostCaptureHandler = event.target.onlostpointercapture;
    }

    function init() {
      let el = document.getElementById('target');
      el.onlostpointercapture = overHandler;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-lostpointercapture-event">Pointer Events – Level 2<br />
<span class="small">The definition of 'onlostpointercapture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onlostpointercapture`

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

## See also

- `Document: lostpointercapture` event
- `HTMLElement: lostpointercapture` event
- [`Element.releasePointerCapture()`](../element/releasepointercapture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onlostpointercapture</a>
