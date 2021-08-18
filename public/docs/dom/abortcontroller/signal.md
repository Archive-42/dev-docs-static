# AbortController.signal

The `signal` read-only property of the [`AbortController`](../abortcontroller) interface returns an [`AbortSignal`](../abortsignal) object instance, which can be used to communicate with/abort a DOM request as desired.

## Syntax

    var signal = abortController.signal;

### Value

An [`AbortSignal`](../abortsignal) object instance.

## Examples

In the following snippet, we aim to download a video using the [Fetch API](../fetch_api).

We first create a controller using the [`AbortController()`](abortcontroller) constructor, then grab a reference to its associated [`AbortSignal`](../abortsignal) object using the [`AbortController.signal`](signal) property.

When the [fetch request](../windoworworkerglobalscope/fetch) is initiated, we pass in the `AbortSignal` as an option inside the request's options object (see `{signal}`, below). This associates the signal and controller with the fetch request and allows us to abort it by calling [`AbortController.abort()`](abort), as seen below in the second event listener.

    var controller = new AbortController();
    var signal = controller.signal;

    var downloadBtn = document.querySelector('.download');
    var abortBtn = document.querySelector('.abort');

    downloadBtn.addEventListener('click', fetchVideo);

    abortBtn.addEventListener('click', function() {
      controller.abort();
      console.log('Download aborted');
    });

    function fetchVideo() {
      ...
      fetch(url, {signal}).then(function(response) {
        ...
      }).catch(function(e) {
        reports.textContent = 'Download error: ' + e.message;
      })
    }

**Note**: When `abort()` is called, the `fetch()` promise rejects with an `AbortError`.

You can find a full working example on GitHub — see [abort-api](https://github.com/mdn/dom-examples/tree/master/abort-api) ([see it running live also](https://mdn.github.io/dom-examples/abort-api/)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-abortcontroller-signal">DOM<br />
<span class="small">The definition of 'signal' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`signal`

66

16

57

No

53

12.1

11.1

Even though `window.AbortController` is defined, it doesn't really abort `fetch` requests. See [bug 174980](https://webkit.org/b/174980).

66

66

57

47

12.2

11.3

Even though `window.AbortController` is defined, it doesn't really abort `fetch` requests. See [bug 174980](https://webkit.org/b/174980).

9.0

## See also

- [Fetch API](../fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal</a>
