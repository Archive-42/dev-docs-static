# Notification.close()

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `close()` method of the [`Notification`](../notification) interface is used to close/remove a previously displayed notification.

**Note:** This API shouldn't be used just to have the notification removed from the screen after a fixed delay since this method will also remove the notification from any notification tray, preventing users from interacting with it after it was initially shown. A valid use for this API would be to remove a notification that is no longer relevant (e.g. the user already read the notification on the webpage in the case of a messaging app or the following song is already playing in a music app).

## Syntax

    Notification.close();

### Parameters

None.

### Returns

Void.

## Examples

In the following snippet, we have a simple function that when called creates an `options` object and then a new notification. At the end of the function, it also calls `close()` inside a [`addEventListener()`](../eventtarget/addeventlistener) function to remove the notification when the relevant content has been read on the webpage.

    function spawnNotification(theBody, theIcon, theTitle) {
      var options = {
        body: theBody,
        icon: theIcon
      };

      var n = new Notification(theTitle,options);
      document.addEventListener('visibilitychange', function() {
        if (document.visibilityState === 'visible') {
          // The tab has become visible so clear the now-stale Notification.
          n.close();
        }
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/">Notifications API</a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`close`

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

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/close</a>
