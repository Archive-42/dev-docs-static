Notification.actions
====================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `actions` read-only property of the [`Notification`](../notification) interface returns the list of [`NotificationAction`](../notificationaction) objects set using the `actions` option when creating the notification using the [`Notification()`](notification) constructor. This is a list of the application-defined actions the user can choose to take immediately within the context of a notification.

**Note:** Device and User Agent might be able to display only a limited number of actions (due to, e.g., limited screen space). This limit can be infered from [`Notification.maxActions`](maxactions).

Syntax
------

    var actions[] = Notification.actions;

### Value

A read-only array of [`NotificationAction`](../notificationaction) objects, each describing a single action the user can choose within a notification.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-actions">Notifications API<br />
<span class="small">The definition of 'actions' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`actions`

53

18

No

No

39

No

No

53

No

41

No

6.0

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)
-   [`Notification.maxActions`](maxactions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/actions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/actions</a>
