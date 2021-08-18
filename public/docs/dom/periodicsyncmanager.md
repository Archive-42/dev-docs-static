# PeriodicSyncManager

**Draft**

This page is not complete.

The `PeriodicSyncManager` interface of the [`Web Periodic Background Synchronization API`](web_periodic_background_synchronization_api) provides a way to register tasks to be run in a service worker at periodic intervals with network connectivity. These tasks are referred to as periodic background sync requests. Access `PeriodicSyncManager` through the [`ServiceWorkerRegistration.periodicSync`](serviceworkerregistration/periodicsync).

## Properties

None.

## Methods

[`PeriodicSyncManager.register`](periodicsyncmanager/register)  
Registers a periodic sync request with the browser with the specified tag and options. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the registration completes.

[`PeriodicSyncManager.getTags`](periodicsyncmanager/gettags)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a list of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing the tags that are currently registered for periodic syncing.

[`PeriodicSyncManager.unregister`](periodicsyncmanager/unregister)  
Unregisters the periodic sync request corresponding to the specified tag and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when unregistration completes.

## Examples

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#periodicsyncmanager">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'PeriodicSyncManager' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`PeriodicSyncManager`

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

## See also

- [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
- [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager</a>
