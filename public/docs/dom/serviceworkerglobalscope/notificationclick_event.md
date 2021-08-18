ServiceWorkerGlobalScope: notificationclick event
=================================================

The `notificationclick` event is fired to indicate that a system notification spawned by [`ServiceWorkerRegistration.showNotification()`](../serviceworkerregistration/shownotification) has been clicked.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../notificationevent"><code>NotificationEvent</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onnotificationclick"><code>onnotificationclick</code></a></td></tr></tbody></table>

Examples
--------

You can use the `notificationclick` event in an [`addEventListener`](../eventtarget/addeventlistener) method:

    self.addEventListener('notificationclick', function(event) {
      console.log('On notification click: ', event.notification.tag);
      event.notification.close();

      // This looks to see if the current is already open and
      // focuses if it is
      event.waitUntil(clients.matchAll({
        type: "window"
      }).then(function(clientList) {
        for (var i = 0; i < clientList.length; i++) {
          var client = clientList[i];
          if (client.url == '/' && 'focus' in client)
            return client.focus();
        }
        if (clients.openWindow)
          return clients.openWindow('/');
      }));
    });

Or use the [`onnotificationclick`](onnotificationclick) event handler property:

    self.onnotificationclick = function(event) {
      console.log('On notification click: ', event.notification.tag);
      event.notification.close();

      // This looks to see if the current is already open and
      // focuses if it is
      event.waitUntil(clients.matchAll({
        type: "window"
      }).then(function(clientList) {
        for (var i = 0; i < clientList.length; i++) {
          var client = clientList[i];
          if (client.url == '/' && 'focus' in client)
            return client.focus();
        }
        if (clients.openWindow)
          return clients.openWindow('/');
      }));
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-serviceworkerglobalscope-onnotificationclick">Notifications API<br />
<span class="small">The definition of 'onnotificationclick' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`notificationclick_event`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

No

40

44

27

11.3

4.0

See also
--------

-   [Service Worker API](../service_worker_api)
-   [Notifications API](../notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/notificationclick_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/notificationclick_event</a>
