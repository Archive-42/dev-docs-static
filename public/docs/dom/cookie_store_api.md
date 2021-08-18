# Cookie Store API

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The Cookie Store API provides an asychronous API for managing cookies, while also exposing cookies to [`service workers`](service_worker_api).

## Concepts and Usage

The existing method of getting and setting cookies involves working with [`document.cookie`](document/cookie) as a string of key/value pairs. In addition to this being cumbersome and error prone, it also has a host of issues in the context of modern web development.

The `document.cookie` interface is [synchronous](https://developer.mozilla.org/en-US/docs/Glossary/Synchronous), single-threaded, and blocking. When writing a cookie you must wait for the browser to update the string of all cookies. In addition, the reliance on [`document`](document) means that cookies cannot be accessed by service workers which cannot access the `document` object.

The Cookie Store API provides an updated method of managing cookies. It is [asynchronous](https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous) and promise-based, therefore does not block the event loop. It does not rely on [`document`](document) and so is available to service workers. The methods for getting and setting cookies also provide more feedback by way of error messages. This means that web developers do not have to set then immediately read back a cookie to check that setting was successful.

## Interfaces

[`CookieStore`](cookiestore)  
The `CookieStore` interface enables getting and setting cookies.

[`CookieStoreManager`](cookiestoremanager)  
The `CookieStoreManager` interface provides a service worker registration to enable service workers to subscribe to cookie change events.

## Events

[`CookieChangeEvent`](cookiechangeevent)  
A `CookieChangeEvent` is dispatched against `CookieStore` objects in [`Window`](window) contexts when any script-visible cookies changes occur.

[`ExtendableCookieChangeEvent`](extendablecookiechangeevent)  
A `ExtendableCookieChangeEvent` is dispatched against [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) events when any script-visible cookie changes have occured which match the service worker's cookie change subscription list.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/">Cookie Store API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Cookie_Store_API`

87

87

No

No

73

No

87

87

No

62

No

14.0

`delete`

87

87

No

No

73

No

87

87

No

62

No

14.0

`get`

87

87

No

No

73

No

87

87

No

62

No

14.0

`getAll`

87

87

No

No

73

No

87

87

No

62

No

14.0

`onchange`

87

87

No

No

73

No

87

87

No

62

No

14.0

`set`

87

87

No

No

73

No

87

87

No

62

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cookie_Store_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cookie_Store_API</a>
