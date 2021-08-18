# CookieStoreManager.subscribe()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `subscribe()` method of the [`CookieStoreManager`](../cookiestoremanager) interface subscribes a [`ServiceWorkerRegistration`](../serviceworkerregistration) to cookie change events.

## Syntax

    let promise = registration.cookies.subscribe(subscriptions);

### Parameters

subscriptions  
An object containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`  
A [`USVString`](../usvstring) with the url of a cookie scope. This may be narrower than the scope of the service worker registration.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`Undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) when the subscription completes.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if the url passed in `subscriptions` does not match the service worker registration's [`scope`](../serviceworkerregistration/scope).

## Examples

In this example the [`ServiceWorkerRegistration`](../serviceworkerregistration) represented by `registration` is subscribing to change events on the cookie named `"cookie1"` with a scope of `"/path1"`.

    const subscriptions = [{ name: 'cookie1', url: `/path1` }];
    await registration.cookies.subscribe(subscriptions);

The url passed to the `subscribe()` method, may be narrower than the service worker registration scope. In the following example the subscription is for `/path/one/`, so it will receive change events for changes on the first cookie, but not the second.

    registration.cookies.subscribe([{name: 'cookie1', url: '/path/one/'}]); // subscription
    cookieStore.set({name: 'cookie1', value: 'cookie-value', path: '/path/one/'}); // recieves a change event
    cookieStore.set({name: 'cookie1', value: 'cookie-value', path: '/path/two/'}); // does not receive a change event

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStoreManager-subscribe">Cookie Store API<br />
<span class="small">The definition of 'CookieStoreManager.subscribe()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`subscribe`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/subscribe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/subscribe</a>
