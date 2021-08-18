# Notification.permission

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `permission` read-only property of the [`Notification`](../notification) interface indicates the current permission granted by the user for the current origin to display web notifications.

## Syntax

    var permission = Notification.permission;

### Value

A [`DOMString`](../domstring) representing the current permission. The value can be:

- `granted`: The user has explicitly granted permission for the current origin to display system notifications.
- `denied`: The user has explicitly denied permission for the current origin to display system notifications.
- `default`: The user decision is unknown; in this case the application will act as if permission was `denied`.

## Examples

The following snippet could be used if you wanted to first check whether notifications are supported, then check if permission has been granted for the current origin to send notifications, then request permission if required, before then sending a notification.

    function notifyMe() {
      // Let's check if the browser supports notifications
      if (!("Notification" in window)) {
        console.log("This browser does not support desktop notification");
      }

      // Let's check whether notification permissions have alredy been granted
      else if (Notification.permission === "granted") {
        // If it's okay let's create a notification
        var notification = new Notification("Hi there!");
      }

      // Otherwise, we need to ask the user for permission
      else if (Notification.permission !== 'denied' || Notification.permission === "default") {
        Notification.requestPermission(function (permission) {
          // If the user accepts, let's create a notification
          if (permission === "granted") {
            var notification = new Notification("Hi there!");
          }
        });
      }

      // At last, if the user has denied notifications, and you
      // want to be respectful there is no need to bother them any more.
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-permission">Notifications API<br />
<span class="small">The definition of 'permission' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`permission`

Yes

14

Yes

No

Yes

7

No

Yes

Yes

Yes

No

Yes

## See also

- [Notifications API](../notifications_api)
- [Using the Notifications API](../notifications_api/using_the_notifications_api)
- [Permissions API](../permissions_api)
- [Using the Permissions API](../permissions_api/using_the_permissions_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/permission" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/permission</a>
