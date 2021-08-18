# CookieStoreManager

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `CookieStoreManager` interface of the <span class="page-not-created">`Cookie Store`</span> API allows service workers to subscribe to events for cookie changes. By using the [`subscribe()`](cookiestoremanager/subscribe) method a particular service worker registration can indicate that it is interested in change events.

A `CookieStoreManager` has an associated [`ServiceWorkerRegistration`](serviceworkerregistration). Each service worker registration has a cookie change subscription list, which is a list of cookie change subscriptions each containing a name and url. The methods in this interface allow the service worker to add and remove subscriptions from this list, and to get a list of all subscriptions.

To get a `CookieStoreManager`, call <span class="page-not-created">`ServiceWorkerRegistration.cookies`</span>.

## Methods

[`CookieStoreManager.getSubscriptions()`](cookiestoremanager/getsubscriptions)  
Returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to a list of the cookie change subscriptions for this service worker registration.

[`CookieStoreManager.subscribe()`](cookiestoremanager/subscribe)  
Subscribes to changes to cookies. It returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the subscription is successful.

[`CookieStoreManager.unsubscribe()`](cookiestoremanager/unsubscribe)  
Unsubscribes the registered service worker from changes to cookies. It returns a [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the operation is successful.

## Examples

In this example the [`ServiceWorkerRegistration`](serviceworkerregistration) represented by `registration` is subscribing to change events on the cookie named `"cookie1"` with a scope of `"/path1"`.

    const subscriptions = [{ name: 'cookie1', url: `/path1` }];
    await registration.cookies.subscribe(subscriptions);

If the [`ServiceWorkerRegistration`](serviceworkerregistration) has subscribed to any cookies then [`getSubscriptions()`](cookiestoremanager/getsubscriptions) will return a list of cookies represented by objects in the same format as used for the original subscription.

    const subscriptions = await registration.cookies.getSubscriptions();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#CookieStoreManager">Cookie Store API<br />
<span class="small">The definition of 'CookieStoreManager' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CookieStoreManager`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CookieStoreManager</a>
