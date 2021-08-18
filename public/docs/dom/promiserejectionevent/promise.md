# PromiseRejectionEvent.promise

The [`PromiseRejectionEvent`](../promiserejectionevent) interface's `promise` read-only property indicates the JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which was rejected. You can examine the event's [`PromiseRejectionEvent.reason`](reason) property to learn why the promise was rejected.

## Syntax

    promise = PromiseRejectionEvent.promise

### Value

The JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which was rejected, and whose rejection went unhandled.

## Examples

This example listens for unhandled promises and, if the [`reason`](reason) is an object with a `code` field containing the text "Module not ready", it sets up an idle callback that will retry the task that failed to execute correctly.

[`event.preventDefault()`](../event/preventdefault) is called to indicate that the promise has now been handled.

    window.onunhandledrejection = function(event) {
      if (event.reason.code && event.reason.code == "Module not ready") {
        window.requestIdleCallback(function(deadline) {
          loadModule(event.reason.moduleName)
            .then(performStartup);
        });
        event.preventDefault();
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-promiserejectionevent-promise">HTML Living Standard<br />
<span class="small">The definition of 'PromiseRejectionEvent.promise' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Promise rejection events](#) in [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [`PromiseRejectionEvent`](../promiserejectionevent)
- `rejectionhandled`
- `unhandledrejection`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/promise" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PromiseRejectionEvent/promise</a>
