# Beacon API

The `Beacon` API is used to send an asynchronous and non-blocking request to a web server. The request does not expect a response. Unlike requests made using [`XMLHttpRequest`](xmlhttprequest) or the [Fetch API](fetch_api), the browser guarantees to initiate beacon requests before the page is unloaded and to run them to completion.

The main use case for the Beacon API is to send analytics such as client-side events or session data to the server. Historically, websites have used [`XMLHttpRequest`](xmlhttprequest) for this, but browsers do not guarantee to send these asynchronous requests in some circumstances (for example, if the page is about to be unloaded). To combat this, websites have resorted to various techniques, such as making the request synchronous, that have a bad effect on responsiveness. Because beacon requests are both asynchronous and guaranteed to be sent, they combine good performance characteristics and reliability.

For more details about the motivation for and usage of this API, see the documentation for the [`navigator.sendBeacon()`](navigator/sendbeacon) method.

**Note:** This API is _not available_ in [Web Workers](web_workers_api) (not exposed via [`WorkerNavigator`](workernavigator)).

## Interfaces

This API defines a single method: [`navigator.sendBeacon()`](navigator/sendbeacon).

The method takes two arguments, the URL and the data to send in the request. The data argument is optional and its type may be an [`ArrayBufferView`](arraybufferview), [`Blob`](blob), [`DOMString`](domstring), or [`FormData`](formdata). If the browser successfully queues the request for delivery, the method returns "`true`"; otherwise, it returns "`false`".

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/beacon/">Beacon</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Beacon_API`

39

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

14

31

No

26

Starting in Opera 46, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

11.1

40

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

42

Starting in Chrome 59, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

31

26

Starting in Opera 46, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

11.3

4.0

Starting in Samsung Internet 7.0, this method cannot send a `Blob` whose type is not CORS safelisted. This is a temporary change until a mitigation can be found for the security issues that this creates. For more information see [Chrome bug 720283](https://crbug.com/720283).

## See also

- [Beacon standard](https://w3c.github.io/beacon/)
- [Beacon CanIUse data](https://caniuse.com/#search=beacon)
- [Intercepting beacons through service workers](https://ehsanakhgari.org/blog/2015-04-08/intercepting-beacons-through-service-workers); Ehsan Akhgari; 2015-Apr-08
- <https://webkit.org/blog/8821/link-click-analytics-and-privacy/>
- [Beaconing in Practice](https://calendar.perfplanet.com/2020/beaconing-in-practice/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Beacon_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Beacon_API</a>
