# Notification

**Note:** This feature is available in [Web Workers](web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Notification` interface of the [Notifications API](notifications_api) is used to configure and display desktop notifications to the user. These notifications' appearance and specific functionality vary across platforms but generally they provide a way to asynchronously provide information to the user.

## Constructor

[`Notification()`](notification/notification)  
Creates a new instance of the `Notification` object.

## Properties

### Static properties

These properties are available only on the `Notification` object itself.

[`Notification.permission`](notification/permission) <span class="badge inline readonly">Read only </span>

A string representing the current permission to display notifications. Possible values are:

- `denied` — The user refuses to have notifications displayed.
- `granted` — The user accepts having notifications displayed.
- `default` — The user choice is unknown and therefore the browser will act as if the value were denied.

[`Notification.maxActions`](notification/maxactions) <span class="badge inline readonly">Read only </span>

### Instance properties

These properties are available only on instances of the `Notification` object.

[`Notification.actions`](notification/actions) <span class="badge inline readonly">Read only </span>  
The actions array of the notification as specified in the constructor's `options` parameter.

[`Notification.badge`](notification/badge) <span class="badge inline readonly">Read only </span>  
The URL of the image used to represent the notification when there is not enough space to display the notification itself.

[`Notification.body`](notification/body) <span class="badge inline readonly">Read only </span>  
The body string of the notification as specified in the constructor's `options` parameter.

[`Notification.data`](notification/data) <span class="badge inline readonly">Read only </span>  
Returns a structured clone of the notification’s data.

[`Notification.dir`](notification/dir) <span class="badge inline readonly">Read only </span>  
The text direction of the notification as specified in the constructor's `options` parameter.

[`Notification.lang`](notification/lang) <span class="badge inline readonly">Read only </span>  
The language code of the notification as specified in the constructor's `options` parameter.

[`Notification.tag`](notification/tag) <span class="badge inline readonly">Read only </span>  
The ID of the notification (if any) as specified in the constructor's `options` parameter.

[`Notification.icon`](notification/icon) <span class="badge inline readonly">Read only </span>  
The URL of the image used as an icon of the notification as specified in the constructor's `options` parameter.

[`Notification.image`](notification/image) <span class="badge inline readonly">Read only </span>  
The URL of an image to be displayed as part of the notification, as specified in the constructor's `options` parameter.

[`Notification.renotify`](notification/renotify) <span class="badge inline readonly">Read only </span>  
Specifies whether the user should be notified after a new notification replaces an old one.

[`Notification.requireInteraction`](notification/requireinteraction) <span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that a notification should remain active until the user clicks or dismisses it, rather than closing automatically.

[`Notification.silent`](notification/silent) <span class="badge inline readonly">Read only </span>  
Specifies whether the notification should be silent — i.e., no sounds or vibrations should be issued, regardless of the device settings.

[`Notification.timestamp`](notification/timestamp) <span class="badge inline readonly">Read only </span>  
Specifies the time at which a notification is created or applicable (past, present, or future).

[`Notification.title`](notification/title) <span class="badge inline readonly">Read only </span>  
The title of the notification as specified in the first parameter of the constructor.

[`Notification.vibrate`](notification/vibrate) <span class="badge inline readonly">Read only </span>  
Specifies a vibration pattern for devices with vibration hardware to emit.

#### Event handlers

[`Notification.onclick`](notification/onclick)  
A handler for the [`click`](element/click_event) event. It is triggered each time the user clicks on the notification.

[`Notification.onclose`](notification/onclose)  
A handler for the [`close`](htmldialogelement/close_event) event. It is triggered when the user closes the notification.

[`Notification.onerror`](notification/onerror)  
A handler for the <span class="page-not-created">`error`</span> event. It is triggered each time the notification encounters an error.

[`Notification.onshow`](notification/onshow)  
A handler for the [`show`](element/show_event) event. It is triggered when the notification is displayed.

## Methods

### Static methods

These methods are available only on the `Notification` object itself.

[`Notification.requestPermission()`](notification/requestpermission)  
Requests permission from the user to display notifications.

### Instance methods

These properties are available only on an instance of the `Notification` object or through its [`prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain). The `Notification` object also inherits from the [`EventTarget`](eventtarget) interface.

[`Notification.close()`](notification/close)  
Programmatically closes a notification instance.

## Examples

Assume this basic HTML:

    <button onclick="notifyMe()">Notify me!</button>

It's possible to send a notification as follows — here we present a fairly verbose and complete set of code you could use if you wanted to first check whether notifications are supported, then check if permission has been granted for the current origin to send notifications, then request permission if required, before then sending a notification.

    function notifyMe() {
      // Let's check if the browser supports notifications
      if (!("Notification" in window)) {
        alert("This browser does not support desktop notification");
      }

      // Let's check whether notification permissions have already been granted
      else if (Notification.permission === "granted") {
        // If it's okay let's create a notification
        var notification = new Notification("Hi there!");
      }

      // Otherwise, we need to ask the user for permission
      else if (Notification.permission !== "denied") {
        Notification.requestPermission().then(function (permission) {
          // If the user accepts, let's create a notification
          if (permission === "granted") {
            var notification = new Notification("Hi there!");
          }
        });
      }

      // At last, if the user has denied notifications, and you
      // want to be respectful there is no need to bother them any more.
    }

We no longer show a live sample on this page, as Chrome and Firefox no longer allow notification permissions to be requested from cross-origin [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)s, with other browsers to follow. To see a example in action, check out our [To-do list example](https://github.com/mdn/to-do-notifications/tree/gh-pages) (also see [the app running live](https://mdn.github.io/to-do-notifications/).)

**Note**: In the above example we spawn notifications in response to a user gesture (clicking a button). This is not only best practice — you should not be spamming users with notifications they didn't agree to — but going forward browsers will explicitly disallow notifications not triggered in response to a user gesture. Firefox is already doing this from version 72, for example.

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

`Notification`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification</a>
