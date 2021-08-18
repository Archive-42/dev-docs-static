ServiceWorkerGlobalScope
========================

The `ServiceWorkerGlobalScope` interface of the [Service Worker API](service_worker_api) represents the global execution context of a service worker.

Developers should keep in mind that the ServiceWorker state is not persisted across the termination/restart cycle, so each event handler should assume it's being invoked with a bare, default global state.

Once successfully registered, a service worker can and will be terminated when idle to conserve memory and processor power. An active service worker is automatically restarted to respond to events, such as [`ServiceWorkerGlobalScope.onfetch`](serviceworkerglobalscope/onfetch) or [`ServiceWorkerGlobalScope.onmessage`](serviceworkerglobalscope/onmessage).

Additionally, synchronous requests are not allowed from within a service worker — only asynchronous requests, like those initiated via the [`fetch()`](windoworworkerglobalscope/fetch) method, can be used.

This interface inherits from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements properties from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers).

Properties
----------

 [`ServiceWorkerGlobalScope.caches`](serviceworkerglobalscope/caches) <span class="badge inline readonly">Read only </span>   
Contains the [`CacheStorage`](cachestorage) object associated with the service worker.

 [`ServiceWorkerGlobalScope.clients`](serviceworkerglobalscope/clients) <span class="badge inline readonly">Read only </span>   
Contains the [`Clients`](clients) object associated with the service worker.

 [`ServiceWorkerGlobalScope.registration`](serviceworkerglobalscope/registration) <span class="badge inline readonly">Read only </span>   
Contains the [`ServiceWorkerRegistration`](serviceworkerregistration) object that represents the service worker's registration.

Events
------

[`activate`](serviceworkerglobalscope/activate_event)  
Occurs when a [`ServiceWorkerRegistration`](serviceworkerregistration) acquires a new [`ServiceWorkerRegistration.active`](serviceworkerregistration/active) worker.  
Also available via the [`ServiceWorkerGlobalScope.onactivate`](serviceworkerglobalscope/onactivate) property.

[`contentdelete`](serviceworkerglobalscope/contentdelete_event)  
Occurs when an item is removed from the [`Content Index`](contentindex).  
Also available via the [`ServiceWorkerGlobalScope.oncontentdelete`](serviceworkerglobalscope/oncontentdelete) property.

`fetch`  
Occurs when a [`fetch()`](windoworworkerglobalscope/fetch) is called.  
Also available via the [`ServiceWorkerGlobalScope.onfetch`](serviceworkerglobalscope/onfetch) property.

[`install`](serviceworkerglobalscope/install_event)  
Occurs when a [`ServiceWorkerRegistration`](serviceworkerregistration) acquires a new [`ServiceWorkerRegistration.installing`](serviceworkerregistration/installing) worker.  
Also available via the [`ServiceWorkerGlobalScope.oninstall`](serviceworkerglobalscope/oninstall) property.

[`message`](serviceworkerglobalscope/message_event)  
Occurs when incoming messages are received. Controlled pages can use the [`MessagePort.postMessage()`](messageport/postmessage) method to send messages to service workers. The service worker can optionally send a response back via the [`MessagePort`](messageport) exposed in [`event.data.port`](https://html.spec.whatwg.org/multipage/comms.html#messageport), corresponding to the controlled page.  
Also available via the [`ServiceWorkerGlobalScope.onmessage`](serviceworkerglobalscope/onmessage) property.

[`notificationclick`](serviceworkerglobalscope/notificationclick_event)  
Occurs when a user clicks on a displayed notification.  
Also available via the [`ServiceWorkerGlobalScope.onnotificationclick`](serviceworkerglobalscope/onnotificationclick) property.

`notificationclose`  
Occurs — when a user closes a displayed notification.  
Also available via the [`ServiceWorkerGlobalScope.onnotificationclose`](serviceworkerglobalscope/onnotificationclose) property.

[`periodicsync`](serviceworkerglobalscope/periodicsync_event)  
Occurs at periodic intervals, which were specified when registering a [`PeriodicSyncManager`](periodicsyncmanager).  
Also available via the [`ServiceWorkerGlobalScope.onperiodicsync`](serviceworkerglobalscope/onperiodicsync) property.

[`push`](serviceworkerglobalscope/push_event)  
Occurs when a server push notification is received.  
Also available via the [`ServiceWorkerGlobalScope.onpush`](serviceworkerglobalscope/onpush) property.

[`pushsubscriptionchange`](serviceworkerglobalscope/pushsubscriptionchange_event)  
Occurs when a push subscription has been invalidated, or is about to be invalidated (e.g. when a push service sets an expiration time).  
Also available via the [`ServiceWorkerGlobalScope.onpushsubscriptionchange`](serviceworkerglobalscope/onpushsubscriptionchange) property.

`sync`  
Triggered when a call to [`SyncManager.register`](syncmanager/register) is made from a service worker client page. The attempt to sync is made either immediately if the network is available or as soon as the network becomes available.  
Also available via the [`ServiceWorkerGlobalScope.onsync`](serviceworkerglobalscope/onsync) property.

Methods
-------

[`ServiceWorkerGlobalScope.skipWaiting()`](serviceworkerglobalscope/skipwaiting)  
Allows the current service worker registration to progress from waiting to active state while service worker clients are using it.

`ServiceWorkerGlobalScope` implements [`WorkerGlobalScope`](workerglobalscope) — which implements [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope). Therefore it also has the following property available to it:

[`GlobalFetch.fetch()`](windoworworkerglobalscope/fetch)  
Starts the process of fetching a resource. This returns a promise that resolves to the [`Response`](response) object representing the response to your request. This algorithm is the entry point for the fetch handling handed to the service worker context.

Examples
--------

This code snippet is from the [service worker prefetch sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/prefetch/service-worker.js) (see [prefetch example live](https://googlechrome.github.io/samples/service-worker/prefetch/).) The [`ServiceWorkerGlobalScope.onfetch`](serviceworkerglobalscope/onfetch) event handler listens for the `fetch` event. When fired, the code returns a promise that resolves to the first matching request in the [`Cache`](cache) object. If no match is found, the code fetches a response from the network.

The code also handles exceptions thrown from the [`fetch()`](windoworworkerglobalscope/fetch) operation. Note that an HTTP error response (e.g., 404) will not trigger an exception. It will return a normal response object that has the appropriate error code set.

    self.addEventListener('fetch', function(event) {
      console.log('Handling fetch event for', event.request.url);

      event.respondWith(
        caches.match(event.request).then(function(response) {
          if (response) {
            console.log('Found response in cache:', response);

            return response;
          }
          console.log('No response found in cache. About to fetch from network...');

          return fetch(event.request).then(function(response) {
            console.log('Response from network is:', response);

            return response;
          }, function(error) {
            console.error('Fetching failed:', error);

            throw error;
          });
        })
      );
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#serviceworkerglobalscope-interface">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ServiceWorkerGlobalScope`

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

`activate_event`

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

`caches`

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

`clients`

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

`cookieStore`

87

87

No

No

73

No

87

87

No

No

No

14.0

`install_event`

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

`message_event`

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

`onabortpayment`

61

≤79

?

No

?

11.1

No

61

?

?

11.3

No

`onactivate`

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

`onbackgroundfetchabort`

74

No

No

No

62

No

No

74

No

53

No

11.0

`onbackgroundfetchclick`

74

No

No

No

62

No

No

74

No

53

No

11.0

`onbackgroundfetchfail`

74

No

No

No

62

No

No

74

No

53

No

11.0

`onbackgroundfetchsuccess`

74

No

No

No

62

No

No

74

No

53

No

11.0

`oncanmakepayment`

61

≤79

?

No

?

?

No

61

?

?

?

No

`oncontentdelete`

No

No

No

No

No

No

Yes

Yes

No

Yes

No

No

`oncookiechange`

87

87

No

No

73

No

87

87

No

No

No

14.0

`onfetch`

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

`oninstall`

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

`onmessage`

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

`onmessageerror`

?

?

?

No

?

Yes

?

?

?

?

Yes

?

`onnotificationclick`

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

`onpaymentrequest`

57

≤79

?

No

?

?

No

57

?

?

?

No

`onperiodicsync`

80

80

No

No

67

No

No

80

No

57

No

13.0

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

`onpushsubscriptionchange`

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

`onsync`

49

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

49

49

44

24

11.3

5.0

`periodicsync_event`

80

80

No

No

67

No

No

80

No

57

No

13.0

`push_event`

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

`pushsubscriptionchange_event`

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

`registration`

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

`serviceWorker`

79

79

No

No

66

No

79

79

No

57

No

12.0

`skipWaiting`

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

-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope</a>
