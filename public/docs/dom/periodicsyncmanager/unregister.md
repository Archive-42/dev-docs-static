PeriodicSyncManager.unregister()
================================

**Draft**

This page is not complete.

The `unregister()` method of the [`PeriodicSyncManager`](../periodicsyncmanager) interface unregisters the periodic sync request corresponding to the specified tag and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when unregistration completes.

Syntax
------

    var unregister = PeriodicSyncManager.unregister(tag);

### Parameters

tag  
The unique [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) descriptor for the specific background sync.

### Return value

A resolved [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

### Exceptions

None.

Examples
--------

The following example removes a periodic sync to stop syncing articles in the background.

    navigator.serviceWorker.ready.then(registration => {
      registration.periodicSync.unregister('get-latest-news');
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#dom-periodicsyncmanager-unregister">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'unregister' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/unregister" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/unregister</a>
