# PromiseRejectionEvent

The `PromiseRejectionEvent` interface represents events which are sent to the global script context when JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)s are rejected. These events are particularly useful for telemetry and debugging purposes.

For details on promise rejection events, see [Promise rejection events](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#promise_rejection_events) in [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises).

## Constructor

[`PromiseRejectionEvent()`](promiserejectionevent/promiserejectionevent)  
Creates a `PromiseRejectionEvent` event, given the type of event (`unhandledrejection` or `rejectionhandled`) and other details.

## Properties

_Also inherits properties from its parent [`Event`](event)_.

[`PromiseRejectionEvent.promise`](promiserejectionevent/promise) <span class="badge inline readonly">Read only </span>  
The JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that was rejected.

[`PromiseRejectionEvent.reason`](promiserejectionevent/reason) <span class="badge inline readonly">Read only </span>  
A value or [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) indicating why the promise was rejected, as passed to [`Promise.reject()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/reject).

## Methods

_This interface has no unique methods; inherits methods from its parent [`Event`](event)_.

## Events

`rejectionhandled`  
Fired when a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected, and after the rejection is handled by the promise's rejection handling code.

`unhandledrejection`  
Fired when a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected but there is no rejection handler to deal with the rejection.

## Examples

This simple example catches unhandled promise rejections and logs them for debugging purposes.

    window.onunhandledrejection = function(e) {
      console.log(e.reason);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#promiserejectionevent">HTML Living Standard<br />
<span class="small">The definition of 'PromiseRejectionEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PromiseRejectionEvent`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

`PromiseRejectionEvent`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

`promise`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

`reason`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

## See also

- [Promises](https://developer.mozilla.org/en-US/docs/Archive/Add-ons/Techniques/Promises)
- [Using promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [`WindowEventHandlers.onrejectionhandled`](windoweventhandlers/onrejectionhandled)
- [`WindowEventHandlers.onunhandledrejection`](windoweventhandlers/onunhandledrejection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent</a>
