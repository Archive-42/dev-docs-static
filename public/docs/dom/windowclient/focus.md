WindowClient.focus()
====================

The `focus()` method of the [`WindowClient`](../windowclient) interface gives user input focus to the current client and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the existing [`WindowClient`](../windowclient).

Syntax
------

    windowClient.focus().then(function(windowClient) {
      // do something with your WindowClient once it has been focused
    });

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the existing [`WindowClient`](../windowclient).

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
          if (client.url == '/' && 'focus' in client)
            return client.focus();
        }
        if (clients.openWindow)
          return clients.openWindow('/');
      }));
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-windowclient-focus">Service Workers<br />
<span class="small">The definition of 'focus()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`focus`

42

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

42

44

?

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/focus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/focus</a>
