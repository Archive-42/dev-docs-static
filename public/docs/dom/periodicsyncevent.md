PeriodicSyncEvent
=================

**Draft**

This page is not complete.

The `PeriodicSyncEvent` interface of the [`Web Periodic Background Synchronization API`](web_periodic_background_synchronization_api) provides a way to run tasks in the service worker with network connectivity.

An instance of this event is passed to the [`ServiceWorkerGlobalScope.onperiodicsync`](serviceworkerglobalscope/onperiodicsync) handler. This happens periodically, at an interval greater than or equal to that set in the [`PeriodicSyncManager.register()`](periodicsyncmanager/register) method. Other implementation-specific factors such as the user's engagement with the site decide the actual interval.

Constructor
-----------

[`PeriodicSyncEvent.PeriodicSyncEvent()`](periodicsyncevent/periodicsyncevent)  
Creates a new `PeriodicSyncEvent` object. This constructor is not typically used. The browser creates these objects itself and provides them to [`ServiceWorkerGlobalScope.onperiodicsync`](serviceworkerglobalscope/onperiodicsync) callback.

Properties
----------

 [`PeriodicSyncEvent.tag`](periodicsyncevent/tag) <span class="badge inline readonly">Read only </span>   
Returns the developer-defined identifier for this `PeriodicSyncEvent`. Multiple tags can be used by the web app to run different periodic tasks at different frequencies.

Methods
-------

Inherits methods from its parent [`ExtendableEvent`](extendableevent).

Examples
--------

The following example shows how to respond to a periodic sync event in the service worker.

    self.addEventListener('periodicsync', event => {
      if (event.tag == 'get-latest-news') {
        event.waitUntil(fetchAndCacheLatestNews());
      }
    });

`fetchAndCacheLatestNews` is a developer defined function.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#periodicsync-event">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'PeriodicSyncEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PeriodicSyncEvent`

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

`PeriodicSyncEvent`

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

`tag`

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

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent</a>
