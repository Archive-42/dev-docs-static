ServiceWorkerGlobalScope.onpush
===============================

The `ServiceWorkerGlobalScope.onpush` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is fired whenever a push message is received by a service worker via a push server.

Syntax
------

    ServiceWorkerGlobalScope.onpush = function(PushEvent) { ... }
    self.addEventListener('push', function(PushEvent) { ... })

Example
-------

The following example takes data from a [`PushEvent`](../pushevent) and displays it on all of the service worker's clients. The data payload of the push message is available in the event object's `data` property ([`PushEvent.data`](../pushevent/data), which contains a [`PushMessageData`](../pushmessagedata) object.)

    self.addEventListener('push', function(event) {
      if (!(self.Notification && self.Notification.permission === 'granted')) {
        return;
      }

      var data = {};
      if (event.data) {
        data = event.data.json();
      }
      var title = data.title || "Something Has Happened";
      var message = data.message || "Here's something you might want to check out.";
      var icon = "images/new-notification.png";

      var notification = new Notification(title, {
        body: message,
        tag: 'simple-push-demo-notification',
        icon: icon
      });

      notification.addEventListener('click', function() {
        if (clients.openWindow) {
          clients.openWindow('https://example.blog.com/2015/03/04/something-new.html');
        }
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/push-api/#dom-serviceworkerglobalscope-onpush">Push API<br />
<span class="small">The definition of 'onpush' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition. This event is specified in the Push API, but accessed through <a href="../serviceworkerglobalscope"><code>ServiceWorkerGlobalScope</code></a>.</td></tr></tbody></table>

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

`onpush`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

40

40

44

24

11.3

4.0

See also
--------

-   [Push API](../push_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onpush" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onpush</a>
