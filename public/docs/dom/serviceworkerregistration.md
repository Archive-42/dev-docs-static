ServiceWorkerRegistration
=========================

The `ServiceWorkerRegistration` interface of the [Service Worker API](service_worker_api) represents the service worker registration. You register a service worker to control one or more pages that share the same origin.

The lifetime of a service worker registration is beyond that of the `ServiceWorkerRegistration` objects that represent them within the lifetime of their corresponding service worker clients. The browser maintains a persistent list of active `ServiceWorkerRegistration` objects.

**Note**: This feature is available in [Web Workers](web_workers_api).

Properties
----------

*Also implements properties from its parent interface,* [`EventTarget`](eventtarget).

 [`ServiceWorkerRegistration.scope`](serviceworkerregistration/scope) <span class="badge inline readonly">Read only </span>   
Returns a unique identifier for a service worker registration. This must be on the same origin as the document that registers the [`ServiceWorker`](serviceworker).

 [`ServiceWorkerRegistration.installing`](serviceworkerregistration/installing) <span class="badge inline readonly">Read only </span>   
Returns a service worker whose state is `installing`. This is initially set to `null`.

 [`ServiceWorkerRegistration.waiting`](serviceworkerregistration/waiting) <span class="badge inline readonly">Read only </span>   
Returns a service worker whose state is `installed`. This is initially set to `null`.

 [`ServiceWorkerRegistration.active`](serviceworkerregistration/active) <span class="badge inline readonly">Read only </span>   
Returns a service worker whose state is `activating` or `activated`. This is initially set to `null`. An active worker will control a [`Client`](client) if the client's URL falls within the scope of the registration (the `scope` option set when [`ServiceWorkerContainer.register`](serviceworkercontainer/register) is first called.)

 [`ServiceWorkerRegistration.navigationPreload`](serviceworkerregistration/navigationpreload) <span class="badge inline readonly">Read only </span>   
Returns the instance of [`NavigationPreloadManager`](navigationpreloadmanager) associated with the current service worker registration.

 [`ServiceWorkerRegistration.pushManager`](serviceworkerregistration/pushmanager) <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`PushManager`](pushmanager) interface for managing push subscriptions including subscribing, getting an active subscription, and accessing push permission status.

 [`ServiceWorkerRegistration.sync`](serviceworkerregistration/sync) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`SyncManager`](syncmanager) interface, which manages background synchronization processes.

 [`ServiceWorkerRegistration.index`](serviceworkerregistration/index) <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`ContentIndex`](contentindex) interface, for managing indexed content for offline viewing.

### Unimplemented properties

 [`serviceWorkerRegistration.periodicSync`](serviceworkerregistration/periodicsync) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`PeriodicSyncManager`](periodicsyncmanager) interface, which manages periodic background synchronization processes. This was mentioned as an idea in the SW explainer at some point, but as yet has not been implemented anywhere.

### Event handlers

 [`ServiceWorkerRegistration.onupdatefound`](serviceworkerregistration/onupdatefound) <span class="badge inline readonly">Read only </span>   
An [`EventListener`](eventlistener) property called whenever an event of type `updatefound` is fired; it is fired any time the [`ServiceWorkerRegistration.installing`](serviceworkerregistration/installing) property acquires a new service worker.

Methods
-------

*Also implements methods from its parent interface,* [`EventTarget`](eventtarget).

[`ServiceWorkerRegistration.getNotifications()`](serviceworkerregistration/getnotifications)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`Notification`](notification) objects.

[`ServiceWorkerRegistration.showNotification()`](serviceworkerregistration/shownotification)  
Displays the notification with the requested title.

[`ServiceWorkerRegistration.update()`](serviceworkerregistration/update)  
Checks the server for an updated version of the service worker without consulting caches.

[`ServiceWorkerRegistration.unregister()`](serviceworkerregistration/unregister)  
Unregisters the service worker registration and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). The service worker will finish any ongoing operations before it is unregistered.

Examples
--------

In this example, the code first checks whether the browser supports service workers and if so registers one. Next, it adds an `updatefound` listener in which it uses the service worker registration to listen for further changes to the service worker's state. If the service worker hasn't changed since the last time it was registered, then the `updatefound` event will not be fired.

    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('/sw.js')
      .then(function(registration) {
        registration.addEventListener('updatefound', function() {
          // If updatefound is fired, it means that there's
          // a new service worker being installed.
          var installingWorker = registration.installing;
          console.log('A new service worker is being installed:',
            installingWorker);

          // You can listen for changes to the installing service worker's
          // state via installingWorker.onstatechange
        });
      })
      .catch(function(error) {
        console.log('Service worker registration failed:', error);
      });
    } else {
      console.log('Service workers are not supported.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#serviceworkerregistration">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/push-api/#dom-serviceworkerregistration-pushmanager">Push API<br />
<span class="small">The definition of 'PushManager' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <a href="pushmanager"><code>pushManager</code></a> property.</td></tr><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/">Notifications API</a></td><td><span class="spec-living">Living Standard</span></td><td>Adds the <a href="serviceworkerregistration/shownotification"><code>showNotification()</code></a> method and the <a href="serviceworkerregistration/getnotifications"><code>getNotifications()</code></a> method.</td></tr><tr class="even"><td><a href="https://wicg.github.io/background-sync/spec/">Web Background Synchronization</a></td><td><span class="spec-living">Living Standard</span></td><td>Adds the <a href="serviceworkerregistration/sync"><code>sync</code></a> property.</td></tr></tbody></table>

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

`ServiceWorkerRegistration`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`active`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`backgroundFetch`

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

`cookies`

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

`getNotifications`

40

17

46

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

No

See [bug 551446](https://crbug.com/551446)

40

46

27

No

4.0

`index`

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

`installing`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`navigationPreload`

59

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

46

No

59

59

44

43

No

4.0

`onupdatefound`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`paymentManager`

56

≤79

?

No

Yes

No

Yes

56

?

Yes

No

No

`periodicSync`

80

80

No

No

No

No

80

80

No

No

No

13.0

`pushManager`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

No

See [bug 421921](https://crbug.com/421921)

40

44

27

No

4.0

`scope`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

No

4.0

`showNotification`

40

17

46

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

No

See [bug 551446](https://crbug.com/551446)

40

46

27

No

4.0

`sync`

49

≤79

No

No

36

No

49

49

No

36

No

4.0

`unregister`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`update`

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

\["Starting with Opera 33, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Opera 35, this method always bypassed the browser cache. Starting with Opera 35, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

11.1

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

44

32

\["Starting with Opera 33, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Opera 35, this method always bypassed the browser cache. Starting with Opera 35, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

No

4.0

\["Starting with Samsung Internet 5.0, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Samsung Internet 5.0, this method always bypassed the browser cache. Starting with Samsung Internet 5.0, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

`updateViaCache`

68

18

57

No

Yes

11.1

68

68

57

Yes

Yes

10.0

`waiting`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

No

4.0

See also
--------

-   [Using Service Workers](service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration</a>
