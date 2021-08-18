# NotificationAction

**Note:** This feature is available in [Web Workers](web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `NotificationAction` interface of the [Notifications API](notifications_api) is used to represent action buttons the user can click to interact with notifications. These buttons' appearance and specific functionality vary across platforms but generally they provide a way to asynchronously show actions to the user in a notification.

## Properties

### Instance properties

These properties are available only on instances of the `Notification` object.

<span class="page-not-created">`NotificationAction.action`</span> <span class="badge inline readonly">Read only </span>  
The name of the action, which can be used to identify the clicked action similar to [input names](index).

<span class="page-not-created">`NotificationAction.title`</span> <span class="badge inline readonly">Read only </span>  
The string describing the action that is displayed to the user.

<span class="page-not-created">`NotificationAction.icon`</span> <span class="badge inline readonly">Read only </span>  
The URL of the image used to represent the notification when there is not enough space to display the notification itself.

## Example

Notifications can fire `notificationclick` events on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope).

Here a service worker shows a notification with a single "Archive" action, allowing users to perform this common task from the notification without having to open the website. The user can also click the main body of the notification to open their inbox instead.

    self.registration.showNotification("New mail from Alice", {
      actions: [
        {
          action: 'archive',
          title: 'Archive'
        }
      ]
    });

    self.addEventListener('notificationclick', function(event) {
      event.notification.close();
      if (event.action === 'archive') {
        // Archive action was clicked
        archiveEmail();
      } else {
        // Main body of notification was clicked
        clients.openWindow('/inbox');
      }
    }, false);

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

`NotificationAction`

22

Before Chrome 22, the support for notification followed an old prefixed version of the specification and used the `navigator.webkitNotifications` object to instantiate a new notification. Before Chrome 32, `Notification.permission` was not supported. Before Chrome 42, service worker additions were not supported. Starting in Chrome 49, notifications do not work in incognito mode.

5

14

22

4

No

25

7

No

See [bug 551446](https://crbug.com/551446)

Yes

22

4

Yes

No

Yes

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

`actions`

53

18

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

`badge`

53

18

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

`body`

Yes

14

26

No

Yes

11

No

Yes

26

Yes

No

Yes

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

`image`

53

18

No

No

40

No

No

53

No

41

No

6.0

`lang`

Yes

14

26

No

Yes

11

No

Yes

26

Yes

No

Yes

`maxActions`

Yes

18

No

No

Yes

No

No

Yes

No

Yes

No

Yes

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

`onclose`

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

`onerror`

Yes

14

No

No

Yes

7

No

Yes

No

Yes

No

Yes

`onshow`

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

`renotify`

50

79

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

`requestPermission`

46

14

47

\["From Firefox 70 onwards, cannot be called from a cross-origin IFrame.", "From Firefox 72 onwards, can only be called in response to a user gesture such as a `click` event."\]

No

40

7

No

46

Yes

41

No

5.0

`requireInteraction`

Yes

17

No

No

Yes

No

No

Yes

No

Yes

No

Yes

`secure_context_required`

62

≤79

67

No

49

?

No

62

67

46

No

8.0

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

`timestamp`

Yes

17

No

No

Yes

No

No

Yes

No

Yes

No

Yes

`title`

Yes

14

26

No

Yes

11

No

Yes

26

Yes

No

Yes

`vibrate`

No

No

No

No

No

No

No

53

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

No

41

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

No

6.0

[Does not work](https://crbug.com/971422) on Android O or later regardless of Chrome version.

`worker_support`

45

≤18

41

No

32

?

No

45

41

32

No

5.0

## See also

- [Using the Notifications API](notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotificationAction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotificationAction</a>
