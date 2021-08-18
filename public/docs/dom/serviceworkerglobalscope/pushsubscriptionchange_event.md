ServiceWorkerGlobalScope: pushsubscriptionchange event
======================================================

The `pushsubscriptionchange` event is sent to the [global scope](../serviceworkerglobalscope) of a [`ServiceWorker`](../serviceworker) to indicate a change in push subscription that was triggered outside the application's control. This may occur if the subscription was refreshed by the browser, but it may also happen if the subscription has been revoked or lost.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><span class="page-not-created"><code>PushSubscriptionChangeEvent</code></span></td></tr><tr class="even"><td>Event handler property</td><td><a href="onpushsubscriptionchange"><code>onpushsubscriptionchange</code></a></td></tr></tbody></table>

Usage notes
-----------

Although examples demonstrating how to share subscription related information with the application server tend to use [`fetch()`](../windoworworkerglobalscope/fetch), this is not necessarily the best choice for real-world use, since it will not work if the app is offline, for example.

Consider using another method to synchronize subscription information between your service worker and the app server, or make sure your code using `fetch()` is robust enough to handle cases where attempts to exchange data fail.

**Note:** In earlier drafts of the specification, this event was defined to be sent when a [`PushSubscription`](../pushsubscription) has expired.

Examples
--------

This example, run in the context of a service worker, listens for a `pushsubscriptionchange` event and re-subscribes to the lapsed subscription.

    self.addEventListener("pushsubscriptionchange", event => {
      event.waitUntil(swRegistration.pushManager.subscribe(event.oldSubscription.options)
        .then(subscription => {
          return fetch("register", {
            method: "post",
            headers: {
              "Content-type": "application/json"
            },
            body: JSON.stringify({
              endpoint: subscription.endpoint
            })
          });
        })
      );
    }, false);

When a `pushsubscriptionchange` event arrives, indicating that the subscription has expired, we resubscribe by calling the push manager's [`subscribe()`](../pushmanager/subscribe) method. When the returned promise is resolved, we receive the new subscription. This is delivered to the app server using a [`fetch()`](../windoworworkerglobalscope/fetch) call to post a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) formatted rendition of the subscription's [`endpoint`](../pushsubscription/endpoint) to the app server.

You can also use the [`onpushsubscriptionchange`](onpushsubscriptionchange) event handler property to set up the event handler:

    self.onpushsubscriptionchange = event => {
      event.waitUntil(swRegistration.pushManager.subscribe(event.oldSubscription.options)
        .then(subscription => {
          /* ... */
        )
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#the-pushsubscriptionchange-event">Push API<br />
<span class="small">The definition of 'pushsubscriptionchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`pushsubscriptionchange_event`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

40

40

44

24

11.3

4.0

See also
--------

-   [Using the Push API](../push_api)
-   [`onpushsubscriptionchange`](onpushsubscriptionchange) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/pushsubscriptionchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/pushsubscriptionchange_event</a>
