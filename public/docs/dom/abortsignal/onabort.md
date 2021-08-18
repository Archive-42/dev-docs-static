# AbortSignal.onabort

The `onabort` read-only property of the [`AbortSignal`](../abortsignal) interface is an event handler Invoked when an `abort` event fires, i.e. when the fetch request(s) the signal is communicating with is/are aborted.

## Syntax

    abortSignal.onabort = function() { ... };

## Examples

In the following snippet, we create a new `AbortController` object, and get its [`AbortSignal`](../abortsignal) (available in the `signal` property). Later on we check whether or not it the signal has been aborted using the `onabort` property, and send an appropriate log to the console.

    var controller = new AbortController();
    var signal = controller.signal;

    signal.onabort = function() {
      console.log('Request aborted');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-abortsignal-aborted">DOM<br />
<span class="small">The definition of 'onabort' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onabort`

66

16

57

No

53

11.1

66

66

57

47

11.3

9.0

## See also

- [Fetch API](../fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/onabort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/onabort</a>
