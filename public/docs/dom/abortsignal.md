# AbortSignal

The `AbortSignal` interface represents a signal object that allows you to communicate with a DOM request (such as a Fetch) and abort it if required via an [`AbortController`](abortcontroller) object.

## Properties

_The AbortSignal interface also inherits properties from its parent interface, [`EventTarget`](eventtarget)._

[`AbortSignal.aborted`](abortsignal/aborted) <span class="badge inline readonly">Read only </span>  
A [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean) that indicates whether the request(s) the signal is communicating with is/are aborted (`true`) or not (`false`).

## Events

Listen to this event using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`abort`  
Invoked when the DOM request(s) the signal is communicating with is/are aborted.  
Also available via the `onabort` property.

## Methods

_The `AbortSignal` interface inherits methods from its parent interface, [`EventTarget`](eventtarget)._

## Static methods

[`AbortSignal.abort()`](abortsignal/abort)  
Returns an `AbortSignal` instance that is already set as aborted.

## Examples

In the following snippet, we aim to download a video using the [Fetch API](fetch_api).

We first create a controller using the [`AbortController()`](abortcontroller/abortcontroller) constructor, then grab a reference to its associated [`AbortSignal`](abortsignal) object using the [`AbortController.signal`](abortcontroller/signal) property.

When the [fetch request](windoworworkerglobalscope/fetch) is initiated, we pass in the `AbortSignal` as an option inside the request's options object (see `{signal}`, below). This associates the signal and controller with the fetch request and allows us to abort it by calling [`AbortController.abort()`](abortcontroller/abort), as seen below in the second event listener.

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

**Note**

When `abort()` is called, the `fetch()` promise rejects with an `AbortError`.

**Warning**

Current versions of Firefox rejects the promise with a `DOMException`

You can find a full working example on GitHub — see [abort-api](https://github.com/mdn/dom-examples/tree/master/abort-api) ([see it running live also](https://mdn.github.io/dom-examples/abort-api/)).

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

`AbortSignal`

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

`aborted`

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

- [Fetch API](fetch_api)
- [Abortable Fetch](https://developers.google.com/web/updates/2017/09/abortable-fetch) by Jake Archibald

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal</a>
