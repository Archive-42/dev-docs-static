PushSubscription.getKey()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getKey()` method of the [`PushSubscription`](../pushsubscription) interface returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representing a client public key, which can then be sent to a server and used in encrypting push message data.

Syntax
------

    var key = subscription.getKey(name);

### Parameters

name  
A [`DOMString`](../domstring) representing the encryption method used to generate a client key. The value can be:

-   `p256dh`: An [Elliptic curve Diffie–Hellman](https://en.wikipedia.org/wiki/Elliptic_curve_Diffie%E2%80%93Hellman) public key on the P-256 curve (that is, the NIST secp256r1 elliptic curve). The resulting key is an uncompressed point in ANSI X9.62 format.
-   `auth`: An authentication secret, as described in<span class="h1"> [Message Encryption for Web Push](https://datatracker.ietf.org/doc/html/draft-ietf-webpush-encryption-08).</span>

### Returns

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

Example
-------

    reg.pushManager.getSubscription()
      .then(function(subscription) {
      // Enable any UI which subscribes / unsubscribes from
      // push messages.

      subBtn.disabled = false;

      if (!subscription) {
        console.log('Not yet subscribed to Push')
        // We aren't subscribed to push, so set UI
        // to allow the user to enable push
        return;
      }

      // Set your UI to show they have subscribed for
      // push messages
      subBtn.textContent = 'Unsubscribe from Push Messaging';
      isPushEnabled = true;

      // initialize status, which includes setting UI elements for subscribed status
      // and updating Subscribers list via push
      var endpoint = subscription.endpoint;
      var key = subscription.getKey('p256dh');
      var auth = subscription.getKey('auth');

        ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/">Push API</a></td><td><span class="spec-wd">Working Draft</span></td><td>This is the Push API spec, but note that <code>getKey()</code> is not currently specified in here. It is currently Firefox-only experimental.</td></tr></tbody></table>

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

`getKey`

42

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

No

42

48

29

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/getKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/getKey</a>
