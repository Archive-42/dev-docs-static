# Notification.icon

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `icon` read-only property of the [`Notification`](../notification) interface contains the URL of an icon to be displayed as part of the notification, as specified in the `icon` option of the [`Notification()`](notification) constructor.

## Syntax

    var icon = Notification.icon;

### Value

A [`USVString`](../usvstring).

## Examples

In our [To-do list app](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view the app running live](https://mdn.github.io/to-do-notifications/)), we use the [`Notification()`](notification) constructor to fire a notification, passing it arguments to specify the body, icon and title we want.

    var notification = new Notification('To do list', {
      body: text,
      icon: img
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-icon">Notifications API<br />
<span class="small">The definition of 'icon' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

## Browser compatibility

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

`icon`

22

5

14

22

4

No

25

11

No

Yes

22

4

Yes

No

Yes

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/icon" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/icon</a>
