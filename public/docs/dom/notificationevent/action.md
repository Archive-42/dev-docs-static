NotificationEvent.action
========================

Returns the string ID of the notification button the user clicked. This value returns an empty string if the user clicked the notification somewhere other than an action button, or the notification does not have a button. The notification id is set during the creation of the Notification via the actions array attribute and can't be modified unless the notification is replaced.

Returns
-------

A [`DOMString`](../domstring) object.

Example
-------

    self.registration.showNotification("New articles available", {
      actions: [{action: "get", title: "Get now."}]
    });

    self.addEventListener('notificationclick', function(event) {
      event.notification.close();
      if (event.action === 'get') {
        synchronizeReader();
      } else {
        clients.openWindow("/reader");
      }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-actions">Notifications API<br />
<span class="small">The definition of 'action' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/action" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent/action</a>
