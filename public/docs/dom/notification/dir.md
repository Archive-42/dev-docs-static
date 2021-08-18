# Notification.dir

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `dir` read-only property of the [`Notification`](../notification) interface indicates the text direction of the notification, as specified in the `dir` option of the [`Notification()`](notification) constructor.

## Syntax

    var direction = Notification.dir;

### Value

A [`DOMString`](../domstring) specifying the text direction. Possible values are:

- `auto`: adopts the browser's language setting behavior (the default.)
- `ltr`: left to right.
- `rtl` : right to left.

**Note**: Most browsers seem to ignore explicit ltr and rtl settings, and just go with the browser-wide setting.

## Examples

The following snippet fires a notification; a simple `options` object is created, then the notification is fired using the `Notification()` constructor.

    var options = {
      body: 'Do you like my body?',
      dir: 'rtl'
    }

    var n = new Notification('Test notification',options);

    console.log(n.dir) // should return 'rtl'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-dir">Notifications API<br />
<span class="small">The definition of 'dir' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`dir`

Yes

14

26

No

Yes

7

No

Yes

26

Yes

No

Yes

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/dir" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/dir</a>
