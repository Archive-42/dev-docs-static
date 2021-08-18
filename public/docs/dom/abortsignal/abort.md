# AbortSignal.abort()

The static `AbortSignal.abort()` method returns an [`AbortSignal`](../abortsignal) that is already set as aborted (and which does not trigger an abort event).

This is shorthand for the following code:

    const controller = new AbortController();
    controller.abort();
    return controller.signal;

This could, for example, be passed to a fetch method in order to run its abort logic (i.e. it may be that code is organised such that the abort logic should be run even if the intended fetch operation has not been started).

**Note**

The method is similar in purpose to [`Promise.reject`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/reject)

## Syntax

    AbortSignal.abort();

### Return value

An `AbortSignal` instance with the [`AbortSignal.aborted`](aborted) property set to `true`.

.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-AbortSignal">DOM<br />
<span class="small">The definition of 'AbortSignal' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`abort`

No

No

88

No

No

No

No

No

88

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort</a>
