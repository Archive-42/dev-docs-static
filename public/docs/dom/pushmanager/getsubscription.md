PushManager.getSubscription()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PushManager.getSubscription()` method of the [`PushManager`](../pushmanager) interface retrieves an existing push subscription.

It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](../pushsubscription) object containing details of an existing subscription. If no existing subscription exists, this resolves to a `null` value.

Syntax
------

    PushManager.getSubscription().then(function(pushSubscription) { ... } );

### Parameters

None.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](../pushsubscription) object or `null`.

Example
-------

This code snippet is taken from a [push messaging and notification sample](https://github.com/GoogleChrome/samples/blob/gh-pages/push-messaging-and-notifications). (No live demo is available.)

    // We need the service worker registration to check for a subscription
      navigator.serviceWorker.ready.then(function(serviceWorkerRegistration) {
        // Do we already have a push message subscription?
        serviceWorkerRegistration.pushManager.getSubscription()
          .then(function(subscription) {
            // Enable any UI which subscribes / unsubscribes from
            // push messages.
            var pushButton = document.querySelector('.js-push-button');
            pushButton.disabled = false;

            if (!subscription) {
              // We aren’t subscribed to push, so set UI
              // to allow the user to enable push
              return;
            }

            // Keep your server in sync with the latest subscriptionId
            sendSubscriptionToServer(subscription);

            showCurlCommand(subscription);

            // Set your UI to show they have subscribed for
            // push messages
            pushButton.textContent = 'Disable Push Messages';
            isPushEnabled = true;
          })
          .catch(function(err) {
            window.Demo.debug.log('Error during getSubscription()', err);
          });
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushmanager-getsubscription">Push API<br />
<span class="small">The definition of 'getSubscription()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSubscription`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

Push enabled by default.

29

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/getSubscription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/getSubscription</a>
