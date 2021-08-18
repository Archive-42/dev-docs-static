# Navigator.sendBeacon()

The `navigator.sendBeacon()` method [asynchronously](https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous) sends a small amount of data over [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) to a web server. It’s intended to be used for sending analytics data to a web server, and avoids some of the problems with legacy techniques for sending analytics, such as the use of [`XMLHttpRequest`](../xmlhttprequest).

## Syntax

    navigator.sendBeacon(url);
    navigator.sendBeacon(url, data);

### Parameters

`url`  
The URL that will receive the data. Can be relative or absolute.

`data` <span class="badge inline optional">Optional</span>  
A [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`ArrayBufferView`](../arraybufferview), [`Blob`](../blob), [`DOMString`](../domstring), [`FormData`](../formdata), or [`URLSearchParams`](../urlsearchparams) object containing the data to send.

### Return values

The `sendBeacon()` method returns `true` if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) successfully queued the `data` for transfer. Otherwise, it returns `false`.

## Description

This method is intended for analytics and diagnostics code to send data to a server.

A problem with sending analytics is that a site often wants to send analytics when the user has finished with a page: for example, when the user navigates to another page. In this situation the browser may be about to unload the page, and in that case the browser may choose not to send asynchronous [`XMLHttpRequest`](../xmlhttprequest) requests.

In the past, web pages have tried to delay page unload long enough to send data. To do this they have used workarounds such as:

- Submitting the data with a blocking synchronous `XMLHttpRequest` call.
- Creating an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element and setting its `src`. Most user agents will delay the unload to load the image.
- Creating a no-op loop for several seconds.

All these methods block unloading the document, which slows down navigation to the next page. There's nothing the next page can do to avoid this, so the new page seems slow, even though it's the fault of the previous page.

With the `sendBeacon()` method, the data is transmitted asynchronously when the user agent has an opportunity to do so, without delaying unload or the next navigation. This means:

- The data is sent reliably
- It's sent asynchronously
- It doesn't impact the loading of the next page

### Sending analytics at the end of a session

Web sites often want to send analytics or diagnostics to the server when the user has finished with the page. The most reliable way to do this is to send the data on the [`visibilitychange`](../document/visibilitychange_event) event:

    document.addEventListener('visibilitychange', function logData() {
      if (document.visibilityState === 'hidden') {
        navigator.sendBeacon('/log', analyticsData);
      }
    });

#### Avoid unload and beforeunload

In the past, many websites have used the [`unload`](../window/unload_event) or [`beforeunload`](../window/beforeunload_event) events to send analytics at the end of a session. However, this is extremely unreliable. In many situations, especially on mobile, the browser will not fire the `unload`, `beforeunload`, or `pagehide` events. For example, these events will not fire in the following situation:

1.  The user loads the page and interacts with it.
2.  When they are finished, they switch to a different app, instead of closing the tab.
3.  Later, they close the browser app using the phone's app manager.

Additionally, the `unload` event is incompatible with the back/forward cache ([bfcache](https://web.dev/bfcache/)) implemented in modern browsers. Some browsers, such as Firefox, handle this incompatibility by excluding pages from the bfcache if they contain unload handlers, thus hurting performance. Others, such as Safari and Chrome on Android, handle it by not firing the `unload` event when the user navigates to another page in the same tab.

Firefox will also exclude pages from the bfcache if they contain `beforeunload` handlers.

#### Use pagehide as a fallback

To support browsers which don't implement `visibilitychange`, use the [`pagehide`](../window/pagehide_event) event. Like `beforeunload` and `unload`, this event is not reliably fired, especially on mobile. However, it is compatible with the bfcache.

## Examples

The following example specifies a handler for the `visibilitychange` event. The handler calls `sendBeacon()` to send analytics.

    document.addEventListener('visibilitychange', function logData() {
      if (document.visibilityState === 'hidden') {
        navigator.sendBeacon('/log', analyticsData);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/beacon/#sendbeacon-method">Beacon<br />
<span class="small">The definition of 'sendBeacon()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`sendBeacon`

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

- The [`visibilitychange`](../document/visibilitychange_event) event.
- [Beacon API](../beacon_api) overview page.
- [Don't lose user and app state, use Page Visibility](https://www.igvita.com/2015/11/20/dont-lose-user-and-app-state-use-page-visibility/) explains in detail why you should use `visibilitychange`, not `beforeunload`/`unload`.
- [Page Lifecycle API](https://developers.google.com/web/updates/2018/07/page-lifecycle-api#developer-recommendations-for-each-state) gives best-practices guidance on handling page lifecyle behavior in your web applications.
- [PageLifecycle.js](https://github.com/GoogleChromeLabs/page-lifecycle): a JavaScript library that deals with cross-browser inconsistencies in page lifecyle behavior.
- [Back/forward cache](https://web.dev/bfcache/) explains what the back/forward cache is, and its implications for various page lifecycle events.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon</a>
