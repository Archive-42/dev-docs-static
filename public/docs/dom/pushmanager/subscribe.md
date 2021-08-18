PushManager.subscribe()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `subscribe()` method of the [`PushManager`](../pushmanager) interface subscribes to a push service.

It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](../pushsubscription) object containing details of a push subscription. A new push subscription is created if the current service worker does not have an existing subscription.

Syntax
------

    PushManager.subscribe(options).then(function(pushSubscription) { ... } );

### Parameters

 `options` <span class="badge inline optional">Optional</span>   
An object containing optional configuration parameters. It can have the following properties:

-   `userVisibleOnly`: A boolean indicating that the returned push subscription will only be used for messages whose effect is made visible to the user.
-   `applicationServerKey`: A Base64-encoded [`DOMString`](../domstring) or [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing an [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) P-256 public key that the push server will use to authenticate your application server. If specified, all messages from your application server must use the [VAPID](https://datatracker.ietf.org/doc/html/rfc8292) authentication scheme, and include a JWT signed with the corresponding private key. This key ***IS NOT*** the same ECDH key that you use to encrypt the data. For more information, see "[Using VAPID with WebPush](https://blog.mozilla.org/services/2016/04/04/using-vapid-with-webpush/)".

***Note:** This parameter is required in some browsers like Chrome and Edge.*

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`PushSubscription`](../pushsubscription) object.

Example
-------

    this.onpush = function(event) {
      console.log(event.data);
      // From here we can write the data to IndexedDB, send it to any open
      // windows, display a notification, etc.
    }

    navigator.serviceWorker.register('serviceworker.js');

    // Use serviceWorker.ready to ensure that you can subscribe for push
    navigator.serviceWorker.ready.then(
      function(serviceWorkerRegistration) {
        var options = {
          userVisibleOnly: true,
          applicationServerKey: applicationServerKey
        };
        serviceWorkerRegistration.pushManager.subscribe(options).then(
          function(pushSubscription) {
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

### Responding to user gestures

`subscribe()` calls should be done in response to a user gesture, such as clicking a button, for example:

    btn.addEventListener('click', function() {
      serviceWorkerRegistration.pushManager.subscribe(options)
      .then(function(pushSubscription) {
        // handle subscription
      });
    })

This is not only best practice — you should not be spamming users with notifications they didn't agree to — but going forward browsers will explicitly disallow notifications not triggered in response to a user gesture. Firefox is already doing this from version 72, for example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushmanager-subscribe">Push API<br />
<span class="small">The definition of 'subscribe()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`subscribe`

42

The `options` parameter with a `applicationServerKey` value is required.

17

44

\["[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.", "From Firefox 72 onwards, can only be called in response to a user gesture such as a `click` event."\]

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/subscribe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/subscribe</a>
