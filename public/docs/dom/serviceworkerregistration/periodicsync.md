ServiceWorkerRegistration.periodicSync
======================================

**Draft**

This page is not complete.

The `periodicSync` read-only property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a reference to the [`PeriodicSyncManager`](../periodicsyncmanager) interface, which allows for registering of tasks to run at specific intervals.

Syntax
------

    var PeriodicSyncManagerObject = ServiceWorkerRegistration.periodicSync;

### Value

A PeriodicSyncManager [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

Examples
--------

You can access the property from either your main script or the registered service worker.

Here is an example from the main script:

    // reference registration
    const registration = await navigator.serviceWorker.ready;

    // feature detection
    if ('periodicSync' in registration) {

      // Background Periodic Sync functionality
      const periodicSync = registration.periodicSync;

    }

From the [`service worker`](../service_worker_api):

    // service worker script

    const periodicSync = self.registration.periodicSync;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#extensions-to-serviceworkerregistration">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'periodicSync' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/periodicSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/periodicSync</a>
