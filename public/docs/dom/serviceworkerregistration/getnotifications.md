ServiceWorkerRegistration.getNotifications()
============================================

The `getNotifications()` method of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a list of the notifications in the order that they were created from the current origin via the current service worker registration. Origins can have many active but differently-scoped service worker registrations. Notifications created by one service worker on the same origin will not be available to other active services workers on that same origin.

Syntax
------

    serviceWorkerRegistration.getNotifications(options)
    .then(function(notificationsList) { ... });

### Parameters

options <span class="badge inline optional">Optional</span>   
An object containing options to filter the notifications returned. The available options are:

-   `tag`: A [`DOMString`](../domstring) representing a notification tag. If specified, only notifications that have this tag will be returned.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a list of [`Notification`](../notification) objects.

Example
-------

    navigator.serviceWorker.register('sw.js');

    var options = { tag : 'user_alerts' };

    navigator.serviceWorker.ready.then(function(registration) {
      registration.getNotifications(options).then(function(notifications) {
        // do something with your notifications
      })
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-serviceworkerregistration-getnotifications">Notifications API<br />
<span class="small">The definition of 'ServiceWorkerRegistration.getNotifications()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`getNotifications`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/getNotifications" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/getNotifications</a>
