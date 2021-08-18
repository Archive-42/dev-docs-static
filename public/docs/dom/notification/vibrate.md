Notification.vibrate
====================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `vibrate` read-only property of the [`Notification`](../notification) interface specifies a [vibration pattern](../vibration_api#vibration_patterns) for the device's vibration hardware to emit when the notification fires. This is specified in the `vibrate` option of the [`Notification()`](notification) constructor.

Syntax
------

    var vibrate = Notification.vibrate;

### Value

A [vibration pattern](../vibration_api#vibration_patterns), as specified in the [Vibration API spec](https://dev.w3.org/2009/dap/vibration/).

Examples
--------

The following snippet is intended to create a notification that also triggers a device vibration; a simple `options` object is created, and then the notification is fired using the `Notification()` constructor.

    var options = {
      body: 'Do you like my body?',
      vibrate: [200, 100, 200]
    }

    var n = new Notification('Test notification',options);

    console.log(n.vibrate) // should log [200,100,200]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-vibrate">Notifications API<br />
<span class="small">The definition of 'vibrate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`vibrate`

No

No

No

No

No

No

No

53

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

No

41

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

No

6.0

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/vibrate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/vibrate</a>
