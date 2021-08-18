# PeriodicSyncManager.getTags()

**Draft**

This page is not complete.

The `getTags()` method of the [`PeriodicSyncManager`](../periodicsyncmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a list of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) objects representing the tags that are currently registered for periodic syncing.

## Syntax

    var tags = PeriodicSyncManager.getTags();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with a list of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) objects representing tags that are currently registered for periodic syncing.

### Exceptions

None.

## Examples

The following example uses the `getTags()` method to check if a periodic sync task with a given tag is registered.

    navigator.serviceWorker.ready.then(registration => {
      registration.periodicSync.getTags().then(tags => {
        if (tags.includes('get-latest-news'))
          skipDownloadingLatestNewsOnPageLoad();
      });
    });

`skipDownloadingLatestNewsOnPageLoad()` is a developer defined function.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#dom-periodicsyncmanager-gettags">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'getTags' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
- [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/getTags" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncManager/getTags</a>
