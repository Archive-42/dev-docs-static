# Notification.data

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `data` read-only property of the [`Notification`](../notification) interface returns a structured clone of the notification's data, as specified in the `data` option of the [`Notification()`](notification) constructor.

The notification's data can be any arbitrary data that you want associated with the notification.

## Syntax

    var data = Notification.data;

### Value

A structured clone.

## Examples

The following snippet fires a notification; a simple `options` object is created, then the notification is fired using the `Notification()` constructor.

    var options = {
      body: 'Do you like my body?',
      data: 'I like peas.'
    }

    var n = new Notification('Test notification',options);

    console.log(n.data) // should return 'I like peas.'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-data">Notifications API<br />
<span class="small">The definition of 'data' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`data`

44

16

34

No

31

No

No

44

34

32

No

4.0

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/data</a>
