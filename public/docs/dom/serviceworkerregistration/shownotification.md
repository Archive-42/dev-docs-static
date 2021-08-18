ServiceWorkerRegistration.showNotification()
============================================

The `showNotification()` method of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface creates a notification on an active service worker.

**Note**: This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    serviceWorkerRegistration.showNotification(title, [options]);

### Parameters

`title`  
The title that must be shown within the notification

 `options` <span class="badge inline optional">Optional</span>   
An object that allows configuring the notification. It can have the following properties:

-   `actions`: An array of actions to display in the notification. The members of the array should be an object literal. It may contain the following values:
    -   action: A [`DOMString`](../domstring) identifying a user action to be displayed on the notification.
    -   title: A [`DOMString`](../domstring) containing action text to be shown to the user.
    -   icon: A [`USVString`](../usvstring) containing the URL of an icon to display with the action.

    Appropriate responses are built using `event.action` within the `notificationclick` event.
-   `badge`: a [`USVString`](../usvstring) containing the URL of an image to represent the notification when there is not enough space to display the notification itself such as for example, the Android Notification Bar. On Android devices, the badge should accommodate devices up to 4x resolution, about 96 by 96 px, and the image will be automatically masked.
-   `body`: A string representing an extra content to display within the notification.
-   `data`: Arbitrary data that you want to be associated with the notification. This can be of any data type.
-   `dir` : The direction of the notification; it can be `auto`, `ltr` or `rtl`
-   `icon`: a [`USVString`](../usvstring) containing the URL of an image to be used as an icon by the notification.
-   `image`: a [`USVString`](../usvstring) containing the URL of an image to be displayed in the notification.
-   `lang`: Specify the lang used within the notification. This string must be a valid [BCP 47 language tag](https://datatracker.ietf.org/doc/html/bcp47).
-   `renotify`: A boolean that indicates whether to suppress vibrations and audible alerts when reusing a `tag` value. If options’s `renotify` is true and options’s `tag` is the empty string a TypeError will be thrown. The default is `false`.
-   `requireInteraction`: Indicates that on devices with sufficiently large screens, a notification should remain active until the user clicks or dismisses it. If this value is absent or false, the desktop version of Chrome will auto-minimize notifications after approximately twenty seconds. The default value is `false`.
-   `silent`: When set indicates that no sounds or vibrations should be made. If options’s `silent` is true and options’s `vibrate` is present a TypeError exception will be thrown. The default value is `false`.
-   `tag`: An ID for a given notification that allows you to find, replace, or remove the notification using a script if necessary.
-   `timestamp`: A [`DOMTimeStamp`](../domtimestamp) representing the time when the notification was created. It can be used to indicate the time at which a notification is actual. For example, this could be in the past when a notification is used for a message that couldn’t immediately be delivered because the device was offline, or in the future for a meeting that is about to start.
-   `vibrate`: A vibration pattern to run with the display of the notification. A vibration pattern can be an array with as few as one member. The values are times in milliseconds where the even indices (0, 2, 4, etc.) indicate how long to vibrate and the odd indices indicate how long to pause. For example, `[300, 100, 400]` would vibrate 300ms, pause 100ms, then vibrate 400ms.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `undefined`.

Examples
--------

    navigator.serviceWorker.register('sw.js');

    function showNotification() {
      Notification.requestPermission(function(result) {
        if (result === 'granted') {
          navigator.serviceWorker.ready.then(function(registration) {
            registration.showNotification('Vibration Sample', {
              body: 'Buzz! Buzz!',
              icon: '../images/touch/chrome-touch-icon-192x192.png',
              vibrate: [200, 100, 200, 100, 200, 100, 200],
              tag: 'vibration-sample'
            });
          });
        }
      });
    }

To invoke the above function at an appropriate time, you could use the [`ServiceWorkerGlobalScope.onnotificationclick`](../serviceworkerglobalscope/onnotificationclick) event handler.

You can also retrieve details of the [`Notification`](../notification)s that have been fired from the current service worker using [`ServiceWorkerRegistration.getNotifications()`](getnotifications).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-serviceworkerregistration-shownotification">Notifications API<br />
<span class="small">The definition of 'showNotification()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`showNotification`

40

17

46

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

No

See [bug 551446](https://crbug.com/551446)

40

46

27

No

4.0

`actions`

45

≤79

No

No

32

No

No

45

No

32

No

5.0

`badge`

53

≤79

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

`data`

44

≤79

No

No

31

No

No

44

No

32

No

4.0

`image`

56

≤79

No

No

43

No

No

56

No

43

No

6.0

`renotify`

50

≤79

No

No

37

No

No

50

No

37

No

5.0

`requireInteraction`

47

≤79

No

No

34

No

No

47

No

34

No

5.0

`vibrate`

45

≤79

No

No

32

No

No

45

No

32

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/showNotification" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/showNotification</a>
