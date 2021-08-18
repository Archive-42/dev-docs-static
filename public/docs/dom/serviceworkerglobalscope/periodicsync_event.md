ServiceWorkerGlobalScope: periodicsync event
============================================

**Draft**

This page is not complete.

The `periodicsync` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is fired at timed intervals, specified when registering a [`PeriodicSyncManager`](../periodicsyncmanager).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../periodicsyncevent"><code>PeriodicSyncEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onperiodicsync"><code>ServiceWorkerGlobalScope.onperiodicsync</code></a></td></tr></tbody></table>

Examples
--------

The following example shows how to respond to a periodic sync event in the service worker.

    self.addEventListener('periodicsync', event => {
      if (event.tag == 'get-latest-news') {
        event.waitUntil(fetchAndCacheLatestNews());
      }
    });

You can also set up the event handler using the [`ServiceWorkerGlobalScope.onperiodicsync`](onperiodicsync) property:

    self.onperiodicsync = (event) => {
      ...
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#extensions-to-serviceworkerregistration">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'periodicsync' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/periodicsync_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/periodicsync_event</a>
