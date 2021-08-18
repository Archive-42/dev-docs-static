# AbortController

The `AbortController` interface represents a controller object that allows you to abort one or more Web requests as and when desired.

You can create a new `AbortController` object using the [`AbortController.AbortController()`](abortcontroller/abortcontroller) constructor. Communicating with a DOM request is done using an [`AbortSignal`](abortsignal) object.

## Constructor

[`AbortController()`](abortcontroller)  
Creates a new `AbortController` object instance.

## Properties

[`AbortController.signal`](abortcontroller/signal) <span class="badge inline readonly">Read only </span>  
Returns a [`AbortSignal`](abortsignal) object instance, which can be used to communicate with/abort a DOM request.

## Methods

[`AbortController.abort()`](abortcontroller/abort)  
Aborts a DOM request before it has completed. This is able to abort [fetch requests](windoworworkerglobalscope/fetch), consumption of any response [`Body`](body), and streams.

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

**Note**: When `abort()` is called, the `fetch()` promise rejects with a `DOMException` named `AbortError`.

You can find a full working example on GitHub — see [abort-api](https://github.com/mdn/dom-examples/tree/master/abort-api) ([see it running live also](https://mdn.github.io/dom-examples/abort-api/)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-abortcontroller">DOM<br />
<span class="small">The definition of 'AbortController' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`AbortController`

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

`AbortController`

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

`abort`

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

- [Fetch API](fetch_api)
- [Abortable Fetch](https://developers.google.com/web/updates/2017/09/abortable-fetch) by Jake Archibald

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbortController" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbortController</a>
