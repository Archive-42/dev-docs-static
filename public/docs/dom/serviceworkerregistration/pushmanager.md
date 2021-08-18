ServiceWorkerRegistration.pushManager
=====================================

The `pushManager` property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a reference to the [`PushManager`](../pushmanager) interface for managing push subscriptions; this includes support for subscribing, getting an active subscription, and accessing push permission status.

Syntax
------

    var pushManager = serviceWorkerRegistration.pushManager;

### Value

A [`PushManager`](../pushmanager) object.

Examples
--------

    this.onpush = function(event) {
      console.log(event.data);
      // From here we can write the data to IndexedDB, send it to any open
      // windows, display a notification, etc.
    }

    navigator.serviceWorker.register('serviceworker.js').then(
      function(serviceWorkerRegistration) {
        serviceWorkerRegistration.pushManager.subscribe().then(
          function(pushSubscription) {
            console.log(pushSubscription.subscriptionId);
            console.log(pushSubscription.endpoint);
            // The push subscription details needed by the application
            // server are now available, and can be sent to it using,
            // for example, an XMLHttpRequest.
          }, function(error) {
            // During development it often helps to log errors to the
            // console. In a production environment it might make sense to
            // also report information about errors back to the
            // application server.
            console.log(error);
          }
        );
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#pushmanager-interface">Push API<br />
<span class="small">The definition of 'PushManager' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pushManager`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

No

See [bug 421921](https://crbug.com/421921)

40

44

27

No

4.0

See also
--------

-   [Push API](../push_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/pushManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/pushManager</a>
