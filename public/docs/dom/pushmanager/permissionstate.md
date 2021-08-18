PushManager.permissionState()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `permissionState()` method of the [`PushManager`](../pushmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`DOMString`](../domstring) indicating the permission state of the push manager. Possible values are `'prompt'`, `'denied'`, or `'granted'`.

**Note**: As of Firefox 44, the permissions for [Notifications](../notifications_api) and [Push](../push_api) have been merged. If permission is granted for notifications, push will also be enabled.

Syntax
------

    PushManager.permissionState(options).then(function(PushMessagingState) { ... });

### Parameters

`options Optional`  
An object containing optional configuration parameters. It can have the following properties:

-   `userVisibleOnly`: A boolean indicating that the returned push subscription will only be used for messages whose effect is made visible to the user.
-   `applicationServerKey`: A public key your push server will use to send messages to client apps via a push server. This value is part of a signing key pair generated by your application server and usable with elliptic curve digital signature (ECDSA) over the P-256 curve.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`DOMString`](../domstring) with a value of `'prompt'`, `'denied'`, or `'granted'`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-pushmanager-permissionstate">Push API<br />
<span class="small">The definition of 'permissionState()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`permissionState`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PushManager/permissionState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PushManager/permissionState</a>