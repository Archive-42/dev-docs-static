Web Periodic Background Synchronization API
===========================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The Web Periodic Background Synchronization API provides a way to register tasks to be run in a [`service worker`](service_worker_api) at periodic intervals with network connectivity. These tasks are referred to as periodic background sync requests.

Web Periodic Background Synchronization Concepts and Usage
----------------------------------------------------------

The Periodic Background Sync API allows web applications to alert their service worker to make any updates, at a periodic time interval. Uses may include fetching latest content whilst a device is connected to wifi, or allowing background updates to an application.

The minimum time interval is set when the API is invoked; however the user agent might also take into account other factors which affect when the service worker receives the event. For instance previous website engagement, or connection to a known network.

The [`PeriodicSyncManager`](periodicsyncmanager) interface is available through [`ServiceWorkerRegistration.periodicSync`](serviceworkerregistration/periodicsync). A unique tag identifier is set to 'name' the sync event, which can then be listened for within the [`ServiceWorker`](serviceworker) script. Once the event is received you can then run any functionality available, such as updating caches or fetching new resources.

As this API relies on service workers, functionality provided by this API is only available in a secure context.

At the time of writing, the Web Periodic Background Synchronization API is only available through an installed [Progressive Web App](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)

Web Periodic Background Synchronization Interfaces
--------------------------------------------------

[`PeriodicSyncManager`](periodicsyncmanager)  
Registers tasks to be run in a service worker at periodic intervals with network connectivity. These tasks are referred to as periodic background sync requests.

[`PeriodicSyncEvent`](periodicsyncevent)  
Represents a synchronization event, sent to the [`global scope`](serviceworkerglobalscope) of a [`ServiceWorker`](serviceworker). It provides a way to run tasks in the service worker with network connectivity.

Service Worker Additions
------------------------

The following additions to the [`Service Worker API`](service_worker_api) are specified in the Periodic Background Sync specification to provide an entry point for using Periodic Background Sync.

 [`ServiceWorkerRegistration.periodicSync`](serviceworkerregistration/periodicsync) <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`PeriodicSyncManager`](periodicsyncmanager) interface for registering tasks to run at specific intervals.

[`ServiceWorkerGlobalScope.onperiodicsync`](serviceworkerglobalscope/onperiodicsync)  
An event handler fired whenever a `periodicsync` event occurs. This happens at timed intervals, that are specified when registering a [`PeriodicSyncManager`](periodicsyncmanager).

Examples
--------

The following examples show how to use the interface.

### Requesting a Periodic Background Sync

The following asynchronous function registers a periodic background sync at a minimum interval of one day from a browsing context:

    async function registerPeriodicNewsCheck() {
      const registration = await navigator.serviceWorker.ready;
      try {
        await registration.periodicSync.register('get-latest-news', {
          minInterval: 24 * 60 * 60 * 1000,
        });
      } catch {
        console.log('Periodic Sync could not be registered!');
      }
    }

### Verifying a Background Periodic Sync by Tag

This code checks to see if a Periodic Background Sync task with a given tag is registered.

    navigator.serviceWorker.ready.then(registration => {
      registration.periodicSync.getTags().then(tags => {
        if (tags.includes('get-latest-news'))
          skipDownloadingLatestNewsOnPageLoad();
      });
    });

### Removing a Periodic Background Sync Task

The following code removes a Periodic Background Sync task to stop articles syncing in the background.

    navigator.serviceWorker.ready.then(registration => {
      registration.periodicSync.unregister('get-latest-news');
    });

### Listening for a Periodic Background Sync within a Service Worker

The following example shows how to respond to a periodic sync event in the service worker.

    self.addEventListener('periodicsync', event => {
      if (event.tag == 'get-latest-news') {
        event.waitUntil(fetchAndCacheLatestNews());
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/">Web Periodic Background Synchronization</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Web_Periodic_Background_Synchronization_API`

80

80

No

No

67

No

80

80

No

57

No

13.0

`getTags`

80

80

No

No

67

No

80

80

No

57

No

13.0

`register`

80

80

No

No

67

No

80

80

No

57

No

13.0

`unregister`

80

80

No

No

67

No

80

80

No

57

No

13.0

See also
--------

-   [An article on using Periodic Background Sync](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Periodic_Background_Synchronization_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Periodic_Background_Synchronization_API</a>
