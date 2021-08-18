SyncManager
===========

The `SyncManager` interface of the [ServiceWorker API](service_worker_api) provides an interface for registering and listing sync registrations.

Properties
----------

None.

Methods
-------

[`SyncManager.register`](syncmanager/register)  
Create a new sync registration and return a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

[`SyncManager.getTags`](syncmanager/gettags)  
Return a list of developer-defined identifiers for SyncManager registration.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-sync/spec/#sync-manager-interface">Web Background Synchronization<br />
<span class="small">The definition of 'SyncManager' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SyncManager`

49

79

No

No

No

No

49

49

No

No

No

5.0

`getTags`

49

79

No

No

No

No

49

49

No

No

No

5.0

`register`

49

79

No

No

No

No

49

49

No

No

No

5.0

`worker_support`

61

49

Only available in the `Window` and `ServiceWorker` global scopes.

79

No

No

No

No

61

49

Only available in the `Window` and `ServiceWorker` global scopes.

61

49

Only available in the `Window` and `ServiceWorker` global scopes.

No

No

No

8.0

5.0

Only available in the `Window` and `ServiceWorker` global scopes.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncManager</a>
