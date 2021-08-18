# PromiseRejectionEvent()

The `PromiseRejectionEvent()` constructor returns a newly created [`PromiseRejectionEvent`](../promiserejectionevent), which represents events fired when a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected. With promise rejection events, it becomes possible to detect and report promises which fail and whose failures go unnoticed. It also becomes easier to write a global handler for errors.

There are two types of `PromiseRejectionEvent`: `unhandledrejection` is sent by the JavaScript runtime when a promise is rejected but the rejection goes unhandled. A `rejectionhandled` event is emitted if a promise is rejected but the rejection is caught by a rejection handler..

## Syntax

    promiseRejectionEvent = PromiseRejectionEvent(type, options);

### Parameters

_The `PromiseRejectionEvent()` constructor also inherits parameters from [`Event()`](../event/event)._

`type`  
A string representing the name of the type of the `PromiseRejectionEvent`. This is case-sensitive and should be one of `"rejectionhandled"` or `"unhandledrejection"`, to match the event names of the possible (non-synthetic) [`PromiseRejectionEvent`](../promiserejectionevent) events that user agents can actually fire).

`options`  
An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) specifying details about the rejection which occurred:

`promise`  
The [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that was rejected.

`reason`  
Any value or [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) which represents the reason the promise was rejected. This can be anything from a numeric error code to an error [`DOMString`](../domstring) to an object which contains detailed information describing the situation resulting in the promise being rejected.

### Return value

A new `PromiseRejectionEvent` configured as specified by the parameters.

## Examples

This example creates a new `unhandledrejection` event for the promise `myPromise` with the reason being the string "My house is on fire". The `reason` could just as easily be a number, or even an object with detailed information including the home address, how serious the fire is, and the phone number of an emergency contact who should be notified.

    let myRejectionEvent = new PromiseRejectionEvent("unhandledrejection", {
      promise : myPromise,
      reason : "My house is on fire"
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-promiserejectionevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'the PromiseRejectionEvent interface' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Promises](https://developer.mozilla.org/en-US/docs/Archive/Add-ons/Techniques/Promises)
- [Using promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [`PromiseRejectionEvent`](../promiserejectionevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/PromiseRejectionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/PromiseRejectionEvent</a>
