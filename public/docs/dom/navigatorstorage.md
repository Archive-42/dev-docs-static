NavigatorStorage
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `NavigatorStorage` [mixin](https://developer.mozilla.org/en-US/docs/Glossary/Mixin) adds to the [`Navigator`](navigator) and [`WorkerNavigator`](workernavigator) interfaces the [`Navigator.storage`](navigatorstorage/storage) property, which provides access to the [`StorageManager`](storagemanager) singleton used for controlling the persistence of data stores as well as obtaining information

**Note:** This feature is available in [Web Workers](web_workers_api).

There are many APIs which provide ways for Web content to store data on a user's computer, including [cookies](https://developer.mozilla.org/en-US/docs/Glossary/Cookie), the Web Storage API ([`Window.localStorage`](window/localstorage) and [`Window.sessionStorage`](window/sessionstorage)), and [IndexedDB](indexeddb_api). The Storage Standard is designed to serve as a common basis for the implementation of all of those APIs and storage technologies, so that their constraints and configurations can be understood and controlled using a common set of methods and properties.

Properties
----------

 [`storage`](navigatorstorage/storage) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>   
Returns the [`StorageManager`](storagemanager) singleton object which is used to access the Storage Manager. Through the returned object, you can control persistence of data stores as well as get estimates of how much space is left for your site or appliation to store data.

Methods
-------

*The `NavigatorStorage` mixin has no methods.*

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

`NavigatorStorage`

55

79

57

No

42

No

55

55

57

42

No

6.0

`storage`

55

79

57

No

42

No

55

55

57

42

No

6.0

See also
--------

-   [`Navigator`](navigator)
-   [`navigator.storage`](navigatorstorage/storage)
-   [`WorkerNavigator`](workernavigator)
-   [`StorageManager`](storagemanager)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage</a>
