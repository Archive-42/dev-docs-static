# Notification.tag

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `tag` read-only property of the [`Notification`](../notification) interface signifies an identifying tag for the notification, as specified in the `tag` option of the [`Notification()`](notification) constructor.

The idea of notification tags is that more than one notification can share the same tag, linking them together. One notification can then be programmatically replaced with another to avoid the users' screen being filled up with a huge number of similar notifications.

## Syntax

    var tag = Notification.tag;

### Value

A [`DOMString`](../domstring).

## Examples

Our [Using the Notifications API](../notifications_api/using_the_notifications_api#dealing_with_repeated_notifications) article has a good example of tag usage.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-tag">Notifications API<br />
<span class="small">The definition of 'tag' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`tag`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/tag" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/tag</a>
