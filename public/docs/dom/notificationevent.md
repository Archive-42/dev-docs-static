# NotificationEvent

The parameter passed into the [`onnotificationclick`](serviceworkerglobalscope/onnotificationclick) handler, the `NotificationEvent` interface represents a notification click event that is dispatched on the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker).

This interface inherits from the [`ExtendableEvent`](extendableevent) interface.

## Constructor

[`NotificationEvent()`](notificationevent/notificationevent)  
Creates a new `NotificationEvent` object.

## Properties

_Inherits properties from its ancestor, [`Event`](event)_.

[`NotificationEvent.notification`](notificationevent/notification) <span class="badge inline readonly">Read only </span>  
Returns a [`Notification`](notification) object representing the notification that was clicked to fire the event.

[`NotificationEvent.action`](notificationevent/action) <span class="badge inline readonly">Read only </span>  
Returns the string ID of the notification button the user clicked. This value returns an empty string if the user clicked the notification somewhere other than an action button, or the notification does not have a button.

## Methods

_Inherits methods from its parent, [`ExtendableEvent`](extendableevent)_.

[`ExtendableEvent.waitUntil()`](extendableevent/waituntil)  
Extends the lifetime of the event. Tells the browser that work is ongoing.

## Example

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#notificationevent">Notifications API<br />
<span class="small">The definition of 'NotificationEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

**Note**: This interface is specified in the [Notifications API](notifications_api), but accessed through [`ServiceWorkerGlobalScope`](serviceworkerglobalscope).

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

`NotificationEvent`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

37

?

No

See [bug 551446](https://crbug.com/551446)

42

44

37

?

4.0

`NotificationEvent`

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

`action`

48

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

No

?

No

48

44

No

?

5.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent</a>
