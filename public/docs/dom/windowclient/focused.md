WindowClient.focused
====================

The `focused` read-only property of the [`WindowClient`](../windowclient) interface is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the current client has focus.

Syntax
------

    var myFocused = windowClient.focused;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

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
          if (client.url == '/' && 'focus' in client) {
            if(!client.focused)
              return client.focus();
            }
          }
        }
        if (clients.openWindow)
          return clients.openWindow('/');
      }));
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-windowclient-focused">Service Workers<br />
<span class="small">The definition of 'WindowClient: focused' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`focused`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

11.1

No

42

44

?

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/focused" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/focused</a>
