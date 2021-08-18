# CookieStoreManager.unsubscribe()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `unsubscribe()` method of the [`CookieStoreManager`](../cookiestoremanager) interface stops the [`ServiceWorkerRegistration`](../serviceworkerregistration) from receiving previously subscribed events.

## Syntax

    let promise = registration.cookies.unsubscribe(subscriptions);

### Parameters

subscriptions  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`  
A [`USVString`](../usvstring) with the url of the scope used to subscribe to this cookie.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`Undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) when the subscription completes.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if the url passed in `subscriptions` does not match the service worker registration's [`scope`](../serviceworkerregistration/scope).

## Examples

In this example the [`ServiceWorkerRegistration`](../serviceworkerregistration) represented by `registration` is unsubscribing from change events on the cookie named `"cookie1"` with a scope of `"/path1"`.

    const subscriptions = [{ name: 'cookie1', url: `/path1` }];
    await registration.cookies.unsubscribe(subscriptions);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStoreManager-unsubscribe">Cookie Store API<br />
<span class="small">The definition of 'CookieStoreManager.unsubscribe()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unsubscribe`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/unsubscribe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/unsubscribe</a>
