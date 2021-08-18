# Notification.requestPermission()

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Note:** This feature is **not** available in [`SharedWorker`](../sharedworker)

**Note**: Safari still uses the callback syntax to get the permission. Read [Using the Notifications API](../notifications_api/using_the_notifications_api) for a good example of how to feature detect this and run code as appropriate.

The `requestPermission()` method of the [`Notification`](../notification) interface requests permission from the user for the current origin to display notifications.

## Syntax

The latest spec has updated this method to a promise-based syntax that works like this:

    Notification.requestPermission().then(function(permission) { ... });

Previously, the syntax was based on a simple callback; this version is now deprecated:

    Notification.requestPermission(callback);

### Parameters

`callback` <span class="badge inline optional">Optional</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
An optional callback function that is called with the permission value. Deprecated in favor of the promise return value.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`DOMString`](../domstring) with the permission picked by the user. Possible values for this string are:

- `granted`
- `denied`
- `default`

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

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/requestPermission" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/requestPermission</a>
