WindowEventHandlers.onunhandledrejection
========================================

The `onunhandledrejection` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `unhandledrejection` events. These events are raised for unhandled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejections.

Syntax
------

    window.onunhandledrejection = function;

### Value

`function` is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) or function to call when `unhandledrejection` events are received by the window. The event handler receives as an input parameter as a [`PromiseRejectionEvent`](../promiserejectionevent).

Examples
--------

This example logs unhandled rejections' `reason` values to the console.

    window.onunhandledrejection = function(e) {
      console.log(e.reason);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-window-onunhandledrejection">HTML Living Standard<br />
<span class="small">The definition of 'onunhandledrejection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onunhandledrejection`

49

79

69

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 and enabled by default in Firefox 69.

No

36

11

49

49

68

55

This event handler was added in Firefox 55 but was disabled since it wasn't fully implemented. It was fully implemented in Firefox 68 but not enabled by default.

No

11.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunhandledrejection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onunhandledrejection</a>
