Notification.timestamp
======================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `timestamp` read-only property of the [`Notification`](../notification) interface returns a [`DOMTimeStamp`](../domtimestamp), as specified in the `timestamp` option of the [`Notification()`](notification) constructor.

The notification's timestamp can represent the time, in milliseconds since 00:00:00 UTC on 1 January 1970, of the event for which the notification was created, or it can be an arbitrary timestamp that you want associated with the notification. For example, a timestamp for an upcoming meeting could be set in the future, whereas a timestamp for a missed message could be set in the past.

Syntax
------

    var timestamp = Notification.timestamp;

### Value

A [`DOMTimeStamp`](../domtimestamp).

Examples
--------

The following snippet fires a notification; a simple `options` object is created, then the notification is fired using the `Notification()` constructor.

    var dts = Math.floor(Date.now());

    var options = {
      body: 'Do you like my body?',
      timestamp: dts
    }

    var n = new Notification('Test notification',options);

    console.log(n.timestamp) // should log original timestamp

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-timestamp">Notifications API<br />
<span class="small">The definition of 'timestamp' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`timestamp`

Yes

17

No

No

Yes

No

No

Yes

No

Yes

No

Yes

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/timestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/timestamp</a>
