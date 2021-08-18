Notification.Notification()
===========================

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Notification()` constructor creates a new [`Notification`](../notification) object instance, which represents a user notification.

Syntax
------

    var notification = new Notification(title, options);

### Parameters

`title`  
Defines a title for the notification, which is shown at the top of the notification window.

 `options` <span class="badge inline optional">Optional</span>   
An options object containing any custom settings that you want to apply to the notification. The possible options are:

-   `dir`: The direction in which to display the notification. It defaults to `auto`, which just adopts the browser's language setting behavior, but you can override that behavior by setting values of `ltr` and `rtl` (although most browsers seem to ignore these settings.)
-   `lang`: The notification's language, as specified using a [`DOMString`](../domstring) representing a [BCP 47 language tag](https://www.rfc-editor.org/rfc/bcp/bcp47.txt). See the Sitepoint [ISO 2 letter language codes](https://www.sitepoint.com/web-foundations/iso-2-letter-language-codes/) page for a simple reference.
-   `badge`: A [`USVString`](../usvstring) containing the URL of the image used to represent the notification when there isn't enough space to display the notification itself.
-   `body`: A [`DOMString`](../domstring) representing the body text of the notification, which is displayed below the title.
-   `tag`: A [`DOMString`](../domstring) representing an identifying tag for the notification.
-   `icon`: A [`USVString`](../usvstring) containing the URL of an icon to be displayed in the notification.
-   `image`: a [`USVString`](../usvstring) containing the URL of an image to be displayed in the notification.
-   `data`: Arbitrary data that you want associated with the notification. This can be of any data type.
-   `vibrate`: A [vibration pattern](../vibration_api#vibration_patterns) for the device's vibration hardware to emit with the notification.
-   `renotify`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) specifying whether the user should be notified after a new notification replaces an old one. The default is `false`, which means they won't be notified.
-   `requireInteraction`: Indicates that a notification should remain active until the user clicks or dismisses it, rather than closing automatically. The default value is `false`.
-   `actions`: An array of [`NotificationAction`](../notificationaction)s representing the actions available to the user when the notification is presented. These are options the user can choose among in order to act on the action within the context of the notification itself. The action's name is sent to the service worker notification handler to let it know the action was selected by the user.
-   `silent`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) specifying whether the notification is silent (no sounds or vibrations issued), regardless of the device settings. The default is `false`, which means it won't be silent.

Example
-------

In our `Emogotchi demo` ([see source code](https://github.com/mdn/emogotchi)), we run a `spawnNotification()` function when we want to trigger a notification. The function is passed parameters to specify the body, icon, and title we want, and then it creates the necessary `options` object and triggers the notification by using the `Notification()` constructor.

    function spawnNotification(body, icon, title) {
      var options = {
          body: body,
          icon: icon
      }
      var notification = new Notification(title, options);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-notification">Notifications API<br />
<span class="small">The definition of 'Notification() constructor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Notification`

22

5

≤18

22

4

No

25

7

No

No

22

4

Yes

No

No

### Chrome notes

Starting in Chrome 49, notifications don't work in incognito mode.

{{Page("/en-US/docs/Web/API/Notifications\_API", "Chrome notes")}}

### Internet Explorer notes

Version 38.14352 and higher of MS Edge Notification API is supported. [Wikipedia - MS Edge](https://en.wikipedia.org/wiki/Microsoft_Edge#Release_history)

IE 11 and lower isn't supported.

See also
--------

-   [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/Notification" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/Notification</a>
