# Notification.onclick

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onclick` property of the [`Notification`](../notification) interface specifies an event listener to receive `click` events. These events occur when the user clicks on a displayed [`Notification`](../notification).

## Syntax

    Notification.onclick = function(event) { ... };

The default behavior is to move the focus to the viewport of the notification's related [browsing context](https://html.spec.whatwg.org/multipage/browsers.html#browsing-context). If you don't want that behavior, call [`preventDefault()`](../event/preventdefault) on the event object.

## Examples

In the following example, we use an onclick handler to open a webpage in a new tab (specified by the inclusion of the `'_blank'` parameter) once a notification is clicked:

    notification.onclick = function(event) {
      event.preventDefault(); // prevent the browser from focusing the Notification's tab
      window.open('http://www.mozilla.org', '_blank');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-onclick">Notifications API<br />
<span class="small">The definition of 'onclick' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

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

`onclick`

Yes

14

22

No

Yes

7

No

Yes

No

Yes

No

Yes

## See also

- [`Notification`](../notification)
- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/onclick" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/onclick</a>
