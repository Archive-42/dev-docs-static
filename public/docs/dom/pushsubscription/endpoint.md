PushSubscription.endpoint
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `endpoint` read-only property of the [`PushSubscription`](../pushsubscription) interface returns a [`USVString`](../usvstring) containing the endpoint associated with the push subscription.

The endpoint takes the form of a custom URL pointing to a push server, which can be used to send a push message to the particular service worker instance that subscribed to the push service. For this reason, it is a good idea to keep your endpoint a secret, so others do not hijack it and abuse the push functionality.

Syntax
------

    var myEnd = pushSubscription.endpoint;

### Value

A [`USVString`](../usvstring).

Example
-------

    navigator.serviceWorker.ready.then(function(reg) {
      reg.pushManager.subscribe({userVisibleOnly: true}).then(function(subscription) {
        console.log(subscription.endpoint);

          // At this point you would most likely send the subscription
          // endpoint to your server, save it, then use it to send a
          // push message at a later date
      })
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushsubscription-endpoint">Push API<br />
<span class="small">The definition of 'endPoint' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`endpoint`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/endpoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription/endpoint</a>
