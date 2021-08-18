WindowClient
============

The `WindowClient` interface of the [ServiceWorker API](service_worker_api) represents the scope of a service worker client that is a document in a browsing context, controlled by an active worker. The service worker client independently selects and uses a service worker for its own loading and sub-resources.

Methods
-------

*`WindowClient` inherits methods from its parent interface, [`Client`](client).*

[`WindowClient.focus()`](windowclient/focus)  
Gives user input focus to the current client.

[`WindowClient.navigate()`](windowclient/navigate)  
Loads a specified URL into a controlled client page.

Properties
----------

*`WindowClient` inherits properties from its parent interface, [`Client`](client).*

 [`WindowClient.focused`](windowclient/focused) <span class="badge inline readonly">Read only </span>   
A boolean that indicates whether the current client has focus.

 [`WindowClient.visibilityState`](windowclient/visibilitystate) <span class="badge inline readonly">Read only </span>   
Indicates the visibility of the current client. This value can be one of `"hidden"`, `"visible"`, or `"prerender"`.

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
            client.focus();
            break;
          }
        }
        if (clients.openWindow)
          return clients.openWindow('/');
      }));
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#windowclient">Service Workers<br />
<span class="small">The definition of 'WindowClient' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`WindowClient`

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

`ancestorOrigins`

?

?

?

No

?

No

No

?

?

?

No

?

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

`navigate`

49

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

?

No

No

49

44

?

No

4.0

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

See also
--------

-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](web_workers_api/using_web_workers)
-   [Channel Messaging API](channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowClient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowClient</a>
