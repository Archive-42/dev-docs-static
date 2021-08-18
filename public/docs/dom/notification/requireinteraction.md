Notification.requireInteraction
===============================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `requireInteraction` read-only property of the [`Notification`](../notification) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that a notification should remain active until the user clicks or dismisses it, rather than closing automatically.

**Note**: This can be set when the notification is first created by setting the `requireInteraction` option to `true` in the options object of the [`Notification.Notification()`](notification) constructor.

Syntax
------

    function spawnNotification(theTitle,theBody,shouldRequireInteraction) {
      var options = {
          body: theBody,
          requireInteraction: shouldRequireInteraction
      }
      var n = new Notification(theTitle,options);
    }

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-requireinteraction">Notifications API<br />
<span class="small">The definition of 'requireInteraction' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

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

`requireInteraction`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/requireInteraction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/requireInteraction</a>
