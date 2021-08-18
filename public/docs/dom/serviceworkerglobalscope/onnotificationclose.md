ServiceWorkerGlobalScope.onnotificationclose
============================================

The `ServiceWorkerGlobalScope.onnotificationclose` property is an event handler called whenever the `notificationclose` event is dispatched on the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) object, that is when a user closes a displayed notification spawned by [`ServiceWorkerRegistration.showNotification()`](../serviceworkerregistration/shownotification).

Notifications created on the main thread or in workers which aren't service workers using the [`Notification()`](../notification/notification) constructor will instead receive a `close` event on the `Notification` object itself.

**Note**: Trying to create a notification inside the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) using the [`Notification()`](../notification/notification) constructor will throw an error.

Syntax
------

    ServiceWorkerGlobalScope.onnotificationclose = function(NotificationEvent) { ... };
    ServiceWorkerGlobalScope.addEventListener('notificationclose', function(NotificationEvent) { ... });

Example
-------

    //Inside a service worker.
    self.onnotificationclose = function(event) {
      console.log('On notification close: ', event.notification.tag);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-serviceworkerglobalscope-onnotificationclose">Notifications API<br />
<span class="small">The definition of 'onnotificationclick' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition. This property is specified on the <a href="../notifications_api"><code>Notifications_API</code></a> even though it's part of <a href="../serviceworkerglobalscope"><code>ServiceWorkerGlobalScope</code></a>.</td></tr></tbody></table>

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

`onnotificationclose`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onnotificationclose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onnotificationclose</a>
