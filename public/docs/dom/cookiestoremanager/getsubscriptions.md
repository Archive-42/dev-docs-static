# CookieStoreManager.getSubscriptions()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getSubscriptions()` method of the [`CookieStoreManager`](../cookiestoremanager) interface returns a list of all the cookie change subscriptions for this [`ServiceWorkerRegistration`](../serviceworkerregistration).

## Syntax

    let promise = registration.cookies.getSubscriptions();

### Return value

A [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a list of objects, each containing:

`name`  
A [`USVString`](../usvstring) with the name of a cookie.

`url`  
A [`USVString`](../usvstring) with the url of the scope used to subscribe to the cookie(s).

## Examples

If the [`ServiceWorkerRegistration`](../serviceworkerregistration) represented by `registration` has subscribed to any cookie change events `subscriptions` will resolve to a list of objects containing the name and url of those cookies.

    const subscriptions = await registration.cookies.getSubscriptions();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStoreManager-getSubscriptions">Cookie Store API<br />
<span class="small">The definition of 'CookieStoreManager.getSubscriptions()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSubscriptions`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/getSubscriptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager/getSubscriptions</a>
