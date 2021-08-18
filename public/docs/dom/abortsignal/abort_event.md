# AbortSignal: abort event

The `abort` event of the [Fetch API](../fetch_api) is fired when a fetch request is aborted, i.e. using [`AbortController.abort()`](../abortcontroller/abort).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><code>onabort</code></td></tr></tbody></table>

## Examples

In the following snippets, we create a new `AbortController` object, and get its [`AbortSignal`](../abortsignal) (available in the `signal` property). Later on we check whether or not it the signal has been aborted using the `onabort` property, and send an appropriate log to the console.

You can use the `abort` event in an `addEventListener` method:

    var controller = new AbortController();
    var signal = controller.signal;

    signal.addEventListener('abort', function() {
     console.log('Request aborted');
    };

Or use the `onabort` event handler property:

    var controller = new AbortController();
    var signal = controller.signal;

    signal.onabort = function() {
      console.log('Request aborted');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-abortsignal-onabort">DOM<br />
<span class="small">The definition of 'abort' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`abort_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort_event</a>
