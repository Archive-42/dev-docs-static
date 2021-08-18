WindowClient.visibilityState
============================

The `visibilityState` read-only property of the [`WindowClient`](../windowclient) interface indicates the visibility of the current client. This value can be one of `"hidden"`, `"visible"`, or `"prerender"`.

Syntax
------

    var myVisState = windowClient.visibilityState;

### Value

A [`DOMString`](../domstring) (See [`Document.visibilityState`](../document/visibilitystate) for values).

Example
-------

    event.waitUntil(clients.matchAll({
        type: "window"
      }).then(function(clientList) {
        for (let i = 0; i < clientList.length; i++) {
          let client = clientList[i];
          if (client.url == '/' && 'focus' in client) {
            if (client.visibilityState === 'hidden')
              return client.focus();
            }
          }
        }

        if (clients.openWindow) {
          return clients.openWindow('/');
        }
      }));
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-windowclient-visibilitystate">Service Workers<br />
<span class="small">The definition of 'visibilityState' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`visibilityState`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/visibilityState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowClient/visibilityState</a>
