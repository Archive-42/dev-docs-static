StorageManager
==============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `StorageManager` interface of the [Storage API](storage_api) provides an interface for managing persistance permissions and estimating available storage. You can get a reference to this interface using either [`navigator.storage`](navigatorstorage/storage) or <span class="page-not-created">`WorkerNavigator.storage`</span>.

Methods
-------

 [`StorageManager.estimate()`](storagemanager/estimate) <span class="notecard inline secure">Secure context</span>   
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`StorageEstimate`](storageestimate) object containing usage and quota numbers for your origin.

 [`StorageManager.persist()`](storagemanager/persist) <span class="notecard inline secure">Secure context</span>   
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if the user agent is able to persist your site's storage.

 [`StorageManager.persisted()`](storagemanager/persisted) <span class="notecard inline secure">Secure context</span>   
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if persistence has already been granted for your site's storage.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#storagemanager">Storage<br />
<span class="small">The definition of 'StorageManger' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StorageManager`

48

≤79

57

51-57

See [bug 1304966](https://bugzil.la/1304966) and [bug 1399038](https://bugzil.la/1399038).

No

Yes

No

48

48

51

See [bug 1304966](https://bugzil.la/1304966) and [bug 1399038](https://bugzil.la/1399038).

Yes

No

5.0

`estimate`

52

≤79

51

No

Yes

No

52

52

51

Yes

No

6.0

`getDirectory`

86

86

No

No

72

No

No

No

No

No

No

No

`persist`

52

48-52

≤79

55

No

Yes

No

52

48-52

52

48-52

55

Yes

No

6.0

5.0-6.0

`persisted`

52

48-52

≤79

55

No

Yes

No

52

48-52

52

48-52

55

Yes

No

6.0

5.0-6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageManager</a>
