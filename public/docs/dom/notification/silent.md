# Notification.silent

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `silent` read-only property of the [`Notification`](../notification) interface specifies whether the notification should be silent, i.e., no sounds or vibrations should be issued, regardless of the device settings. This is specified in the `silent` option of the [`Notification()`](notification) constructor.

## Syntax

    var silent = Notification.silent;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). `false` is the default; `true` makes the notification silent.

## Examples

The following snippet is intended to fire a silent notification; a simple `options` object is created, and then the notification is fired using the [`Notification()`](notification) constructor.

    var options = {
      body: 'Do you like my body?',
      silent: true
    }

    var n = new Notification('Test notification', options);

    console.log(n.silent) // should log true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-silent">Notifications API<br />
<span class="small">The definition of 'silent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`silent`

43

17

No

No

30

No

No

43

No

30

No

4.0

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/silent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/silent</a>
