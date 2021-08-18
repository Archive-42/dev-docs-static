ServiceWorkerRegistration.sync
==============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `sync` property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a reference to the [`SyncManager`](../syncmanager) interface, which manages background synchronization processes.

Syntax
------

    var syncManager = serviceWorkerRegistration.sync;

### Value

A [`SyncManager`](../syncmanager) object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-sync/spec/">Web Background Synchronization</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/sync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/sync</a>
