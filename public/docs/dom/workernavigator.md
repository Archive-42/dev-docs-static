WorkerNavigator
===============

The `WorkerNavigator` interface represents a subset of the [`Navigator`](navigator) interface allowed to be accessed from a [`Worker`](worker). Such an object is initialized for each worker and is available via the [`WorkerGlobalScope.navigator`](workerglobalscope/navigator) property obtained by calling `self.navigator`.

Properties
----------

*The `WorkerNavigator` interface implements properties from the [`NavigatorID`](navigatorid), [`NavigatorLanguage`](navigatorlanguage), [`NavigatorOnLine`](navigatoronline), <span class="page-not-created">`NavigatorDataStore`</span>, and [`NavigatorConcurrentHardware`](navigatorconcurrenthardware) interfaces.*

 [`WorkerNavigator.connection`](workernavigator/connection)<span class="badge inline readonly">Read only </span>   
Provides a [`NetworkInformation`](networkinformation) object containing information about the network connection of a device.

 [`WorkerNavigator.locks`](workernavigator/locks) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a [`LockManager`](lockmanager) object which provides methods for requesting a new [`Lock`](lock) object and querying for an existing `Lock` object.

 [`WorkerNavigator.permissions`](workernavigator/permissions) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a [`Permissions`](permissions) object that can be used to query and update permission status of APIs covered by the [Permissions API](permissions_api).

 [`WorkerNavigator.serial`](workernavigator/serial) <span class="badge inline readonly">Read only </span>   
Returns a [`Serial`](serial) object, which represents the entry point into the <span class="page-not-created">`Web Serial API`</span> to enable the control of serial ports.

 [`NavigatorStorage.storage`](navigatorstorage/storage)<span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`StorageManager`](storagemanager) interface for managing persistance permissions and estimating available storage.

### Inherited properties

 [`NavigatorID.appCodeName`](navigatorid/appcodename) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Always returns `'Mozilla'`, in any browser. This property is kept only for compatibility purposes.

 [`NavigatorID.appName`](navigatorid/appname) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns the official name of the browser. Do not rely on this property to return the correct value.

 [`NavigatorID.appVersion`](navigatorid/appversion) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns the version of the browser as a string. Do not rely on this property to return the correct value.

 [`NavigatorConcurrentHardware.hardwareConcurrency`](navigatorconcurrenthardware/hardwareconcurrency)<span class="badge inline readonly">Read only </span>   
Returns the number of logical processor cores available.

 [`NavigatorLanguage.language`](navigatorlanguage/language)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the language version of the browser. The `null` value is returned when this is unknown.

 [`NavigatorLanguage.languages`](navigatorlanguage/languages)<span class="badge inline readonly">Read only </span>   
Returns an array of [`DOMString`](domstring)s representing the languages known to the user, in order of preference.

 [`NavigatorOnLine.onLine`](navigatoronline/online)<span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the browser is online.

 [`NavigatorID.platform`](navigatorid/platform) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Returns a string representing the platform of the browser. Do not rely on this property to return the correct value.

 [`NavigatorID.product`](navigatorid/product) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="badge inline readonly">Read only </span>   
Always returns `'Gecko'`, on any browser. This property is kept only for compatibility purposes.

 [`NavigatorID.userAgent`](navigatorid/useragent)<span class="badge inline readonly">Read only </span>   
Returns the user agent string for the current browser.

Methods
-------

*The `WorkerNavigator` interface implements methods from the [`NavigatorID`](navigatorid), [`NavigatorLanguage`](navigatorlanguage) and [`NavigatorOnLine`](navigatoronline) interfaces.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workernavigator">HTML Living Standard<br />
<span class="small">The definition of 'WorkerNavigator' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`WorkerNavigator`

1

≤79

3.5

?

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`connection`

61

≤79

No

No

Yes

No

50

38

53

37

No

3.0

`permissions`

43

≤79

No

No

30

No

No

See [bug 490120](https://crbug.com/490120)

43

No

30

No

4.0

`serial`

89

89

No

No

No

No

No

No

No

No

No

No

`serviceWorker`

?

?

?

No

?

Yes

?

?

?

?

Yes

?

See also
--------

-   Other Worker-related interfaces: [`Worker`](worker), [`WorkerLocation`](workerlocation), and [`WorkerGlobalScope`](workerglobalscope).
-   [Using web workers.](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator</a>
