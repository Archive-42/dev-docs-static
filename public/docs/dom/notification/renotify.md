Notification.renotify
=====================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `renotify` read-only property of the [`Notification`](../notification) interface specifies whether the user should be notified after a new notification replaces an old one, as specified in the `renotify` option of the [`Notification()`](notification) constructor.

Syntax
------

    var renotify = Notification.renotify;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). `false` is the default; `true` makes the notification renotify the user.

Examples
--------

The following snippet is intended to fire a notification that renotifies the user after it has been replaced; a simple `options` object is created, and then the notification is fired using the `Notification()` constructor.

    var options = {
      body: 'Do you like my body?',
      renotify: true
    }

    var n = new Notification('Test notification',options);

    console.log(n.renotify) // should log true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-renotify">Notifications API<br />
<span class="small">The definition of 'renotify' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`renotify`

50

79

No

No

37

No

No

50

No

37

No

5.0

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/renotify" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/renotify</a>
