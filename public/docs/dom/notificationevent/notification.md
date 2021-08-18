# NotificationEvent.notification

The `notification` read-only property of the [`NotificationEvent`](../notificationevent) interface returns the instance of the [`Notification`](../notification) that was clicked to fire the event. The [`Notification`](../notification) provides read-only access to many properties that were set at the instantiation time of the Notification such as `tag` and `data` attributes that allow you to store information for deferred use in the `notificationclick` event.

## Returns

A [`Notification`](../notification) object.

## Example

    self.addEventListener('notificationclick', function(event) {
      console.log('On notification click');

      // Data can be attached to the notification so that you
      // can process it in the notificationclick handler.
      console.log('Notification Tag:', event.notification.tag);
      console.log('Notification Data:', event.notification.data);
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notificationevent-notification">Notifications API<br />
<span class="small">The definition of 'notification' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

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

`notification`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

?

No

42

44

37

?

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/notification" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/notification</a>
