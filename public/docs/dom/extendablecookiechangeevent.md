# ExtendableCookieChangeEvent

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `ExtendableCookieChangeEvent` interface of the [`Cookie Store API`](cookie_store_api) is the event type passed to <span class="page-not-created">`ServiceWorkerRegistration.oncookiechange()`</span> when any cookie changes have occured. A cookie change event consists of a cookie and a type (either "changed" or "deleted".)

Cookie changes that cause the `ExtendableCookieChangeEvent` to be dispatched are:

- A cookie is newly created and not immediately removed. In this case `type` is "changed".
- A cookie is newly created and immediately removed. In this case `type` is "deleted"
- A cookie is removed. In this case `type` is "deleted".

**Note**

A cookie that is replaced due to the insertion of another cookie with the same name, domain, and path, is ignored and does not trigger a change event.

## Constructor

[`ExtendableCookieChangeEvent.ExtendableCookieChangeEvent()`](extendablecookiechangeevent/extendablecookiechangeevent)  
Creates a new `ExtendableCookieChangeEvent`.

## Properties

_This interface also inherits properties from [`ExtendableEvent`](extendableevent)._

[`ExtendableCookieChangeEvent.changed`](extendablecookiechangeevent/changed)<span class="badge inline readonly">Read only </span>  
Returns an array containing the changed cookies.

[`ExtendableCookieChangeEvent.deleted`](extendablecookiechangeevent/deleted)<span class="badge inline readonly">Read only </span>  
Returns an array containing the deleted cookies.

## Examples

In the below example we use [`CookieStoreManager.getSubscriptions()`](cookiestoremanager/getsubscriptions) to get a list of existing subscriptions. (In service workers, a subscription is required in order to listen for events.) We unsubscribe from existing subscriptions using [`CookieStoreManager.unsubscribe()`](cookiestoremanager/unsubscribe), then subscribe to the cookie with a name of 'COOKIE_NAME' using [`CookieStoreManager.subscribe()`](cookiestoremanager/subscribe). If that cookie is changed, the event listener logs the event to the console. This will be an `ExtendableCookieChangeEvent` object, with the [`changed`](extendablecookiechangeevent/changed) or [`deleted`](extendablecookiechangeevent/deleted) property containing the modified cookie.

    self.addEventListener('activate', (event) => {
      event.waitUntil(async () => {
        const subscriptions = await self.registration.cookies.getSubscriptions();
        await self.registration.cookies.unsubscribe(subscriptions);

        await self.registration.cookies.subscribe([
          {
            name: 'COOKIE_NAME',
          }
        ]);
      });
    });

    self.addEventListener('cookiechange', event => {
      console.log(event);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/cookie-store/#ExtendableCookieChangeEvent">Cookie Store API<br />
<span class="small">The definition of 'ExtendableCookieChangeEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ExtendableCookieChangeEvent`

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

`ExtendableCookieChangeEvent`

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

`changed`

87

87

No

No

73

No

No

87

No

62

No

14.0

`deleted`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ExtendableCookieChangeEvent</a>
