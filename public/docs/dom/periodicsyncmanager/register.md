PeriodicSyncManager.register()
==============================

**Draft**

This page is not complete.

The `register()` method of the [`PeriodicSyncManager`](../periodicsyncmanager) interface registers a periodic sync request with the browser with the specified tag and options. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the registration completes.

Syntax
------

    var register = PeriodicSyncManager.register(tag, BackgroundSyncOptions);

### Parameters

*tag*  
A unique [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) identifier

 *BackgroundSyncOptions* <span class="badge inline optional">Optional</span>   
An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) containing the following optional data:

-   `minInterval`: The minimum interval time, in milliseconds, at which the periodic sync should occur.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

InvalidStateError  
There is no active [`ServiceWorker`](../serviceworker) present.

NotAllowedError  
If permission for background periodic sync is not granted.

InvalidAccessError  
The active window is not the main window (not of "auxiliary" or "top-level" type).

Examples
--------

The following asynchronous function registers a periodic background sync at a minimum interval of one day from a browsing context:

    async function registerPeriodicNewsCheck() {
      const registration = await navigator.serviceWorker.ready;
      try {
        await registration.periodicSync.register('fetch-news', {
          minInterval: 24 * 60 * 60 * 1000,
        });
      } catch {
        console.log('Periodic Sync could not be registered!');
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#dom-periodicsyncmanager-register">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'register' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/register" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/register</a>
