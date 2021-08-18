Storage API
===========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Note:** This feature is available in [Web Workers](web_workers_api).

The Storage Standard defines a common, shared storage system to be used by all APIs and technologies that store content-accessible data for individual Web sites. The Storage API gives sites' code the ability to find out how much space they can use, how much they are already using, and even control whether or not they need to be alerted before the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) disposes of site data in order to make room for other things.

Site storage—the data stored for a Web site which is managed by the Storage Standard—includes:

-   [IndexedDB databases](indexeddb_api)
-   [Cache API data](cache)
-   [Service Worker registrations](service_worker_api)
-   [Web Storage API data](web_storage_api) managed using [`window.localStorage`](window/localstorage)
-   History state information saved using [`History.pushState()`](history/pushstate)
-   [Application caches](https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache) (highly deprecated!)
-   [Notification data](notifications_api)
-   Other kinds of site-accessible, site-specific data that may be maintained

Site storage units
------------------

The site storage system described by the Storage Standard and interacted with using the Storage API consists of a single **site storage unit** for each [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin). In essence, every Web site or Web application has its own storage unit into which its data gets placed. The diagram below shows a site storage pool with three storage units within, showing how storage units can have different data types stored within and may have different quotas (maximum storage limits).

<img src="data:image/png;base64,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" alt="A diagram showing how the site storage pool consists of multiple storage units that contain data from various APIs as well as possible unused space left before the quota is reached." width="746" height="512" />

-   Origin 1 has some Web Storage data as well as some IndexedDB data, but also has some free space left; its current usage hasn't yet reached its quota.
-   Origin 2 has no data stored in it yet; it's just an empty box waiting for content. This origin, however, has a lower quota than the other two do. It may be a less-visited site, or one known to have lower data storage requirements.
-   Origin 3's storage unit is completely full; it's reached its quota and can't store any more data without some existing material being removed.

[User agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) are likely to use various techniques to determine the quota for various origins. One of the most likely methods—one which the specification specifically encourages, in fact—would be to consider the popularity and/or usage levels of individual sites to determine what their quotas should be. It's also conceivable that the browser might offer a user interface to customize these quotas.

Box modes
---------

The actual data storage within each site storage unit is called its **box**. Each site storage unit has exactly one box into which all of its data is placed, and has a **box mode** that describes the data retention policy for that box. There are two modes:

`"best-effort"`  
The user agent will try to retain the data contained in the box for as long as it can, *but will not warn users* if storage space runs low and it becomes necessary to clear the box in order to relieve the storage pressure.

`"persistent"`  
The user agent will retain the data as long as possible, clearing all `"best-effort"` boxes before considering clearing a box marked `"persistent"`. If it becomes necessary to consider clearing persistent boxes, the user agent will notify the user and provide a way to clear one or more persistent boxes as needed.

To change an origin's box mode requires permission to use the `"persistent-storage"` feature.

Data persistence and clearing
-----------------------------

If the site or app has the `"persistent-storage"` feature permission, it can use the [`StorageManager.persist()`](storagemanager/persist) method to request that its box be made persistent. It's also possible for the user agent to decide to make the site's storage unit persistent due to usage characteristics or other metrics. The `"persistent-storage"` feature's permission-related flags, algorithms, and types are all set to the standard defaults for a permission, except that the **permission state** must be the same across the entire origin, and that if the permission state isn't `"granted"` (meaning that for whatever reason, access to the persistent storage feature was denied), the origin's site storage unit's box mode is always `"best-effort"`.

**Note**: See [Using the Permissions API](permissions_api/using_the_permissions_api) for further details about obtaining and managing permissions.

When clearing site storage units, an origin's box is treated as a single entity; if the user agent needs to clear it and the user approves, the entire data store is cleared rather than providing some means of clearing only data from individual APIs.

If a box is marked as `"persistent"`, the contents won't be cleared by the user agent without either the data's origin itself or the user specifically doing so. This includes scenarios such as the user selecting a "Clear Caches" or "Clear Recent History" option. The user will be asked specifically for permission to remove persistent site storage units.

Quotas and usage estimates
--------------------------

The user agent determines, using whatever mechanism it chooses, the maximum amount of storage a given site can use. This maximum is the origin's **quota**. The amount of this space which is in use by the site is called its **usage**. Both of these values are estimates; there are several reasons why they're not precise:

-   User agents are encouraged to obscure the exact size of the data used by a given origin, to prevent these values from being used for fingerprinting purposes.
-   De-duplication, compression, and other methods to reduce the physical size of the stored data may be used.
-   Quotas are conservative estimates of the space available for the origin's use, and should be less than the available space on the device to help prevent overruns.

User agents may use any method they choose to determine the size of origins' quotas, and are encouraged by the specification to provide popular or frequently-used sites with extra space.

To determine the estimated quota and usage values for a given origin, use the [`navigator.storage.estimate()`](storagemanager/estimate) method, which returns a promise that, when resolved, receives a [`StorageEstimate`](storageestimate) that contains these figures. For example:

    navigator.storage.estimate().then(estimate => {
      // estimate.quota is the estimated quota
      // estimate.usage is the estimated number of bytes used
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/">Storage</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Storage_API`

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

BCD tables only load in the browser

See also
--------

-   [`navigator.storage`](navigatorstorage/storage)
-   [`StorageManager`](storagemanager) (the object returned by `navigator.storage`)
-   [Using the Permissions API](permissions_api/using_the_permissions_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage_API</a>
