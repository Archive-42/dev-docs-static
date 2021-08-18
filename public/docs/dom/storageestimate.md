StorageEstimate
===============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `StorageEstimate` dictionary is used by the [`StorageManager`](storagemanager) to provide estimates of the size of a site's or application's data store and how much of it is in use. The [`estimate()`](storagemanager/estimate) method returns an object that conforms to this dictionary when its [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves.

These values are only estimates for several reasons, including both performance and preventing storage capacity data from being used for fingerprinting purposes. See the individual property pages for details.

Properties
----------

 [`quota`](storageestimate/quota) <span class="notecard inline secure">Secure context</span>   
A numeric value in bytes which provides a conservative approximation of the total storage the user's device or computer has available for the site origin or Web app. It's possible that there's more than this amount of space available though you can't rely on that being the case.

 [`usage`](storageestimate/usage) <span class="notecard inline secure">Secure context</span>   
A numeric value in bytes approximating the amount of storage space currently being used by the site or Web app, out of the available space as indicated by `quota`. Unit is byte.

 <span class="page-not-created">`usageDetails`</span> <span class="notecard inline secure">Secure context</span>   
A dictionary containing a breakdown of `usage` by storage system. All included members will have a `usage` greater than 0 and any storage system with 0 `usage` will be excluded from the dictionary.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#dictdef-storageestimate">Storage<br />
<span class="small">The definition of 'StorageEstimate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StorageEstimate`

52

≤79

51

No

42

No

52

52

51

42

No

6.0

`quota`

52

≤79

51

No

42

No

52

52

51

42

No

6.0

`usage`

52

≤79

51

No

42

No

52

52

51

42

No

6.0

See also
--------

-   [Storage API](storage_api)
-   [`StorageManager`](storagemanager)
-   [`StorageManager.estimate()`](storagemanager/estimate)
-   [`navigator.storage`](navigatorstorage/storage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageEstimate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageEstimate</a>
