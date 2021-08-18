WorkerGlobalScope
=================

The `WorkerGlobalScope` interface of the [Web Workers API](web_workers_api) is an interface representing the scope of any worker. Workers have no browsing context; this scope contains the information usually conveyed by [`Window`](window) objects — in this case event handlers, the console or the associated [`WorkerNavigator`](workernavigator) object. Each `WorkerGlobalScope` has its own event loop.

This interface is usually specialized by each worker type: [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope) for dedicated workers, [`SharedWorkerGlobalScope`](sharedworkerglobalscope) for shared workers, and [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) for [ServiceWorker](service_worker_api). The `self` property returns the specialized scope for each context.

Properties
----------

*This interface inherits properties from the [`EventTarget`](eventtarget) interface and [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) and [`WindowEventHandlers`](windoweventhandlers) mixins.*

### Standard properties

 [`WorkerGlobalScope.navigator`](workerglobalscope/navigator) <span class="badge inline readonly">Read only </span>   
Returns the [`WorkerNavigator`](workernavigator) associated with the worker. It is a specific navigator object, mostly a subset of the [`Navigator`](navigator) for browsing scopes, but adapted to workers.

 [`WorkerGlobalScope.self`](workerglobalscope/self) <span class="badge inline readonly">Read only </span>   
Returns a reference to the `WorkerGlobalScope` itself. Most of the time it is a specific scope like [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope), [`SharedWorkerGlobalScope`](sharedworkerglobalscope) or [`ServiceWorkerGlobalScope`](serviceworkerglobalscope).

 [`WorkerGlobalScope.location`](workerglobalscope/location) <span class="badge inline readonly">Read only </span>   
Returns the [`WorkerLocation`](workerlocation) associated with the worker. It is a specific location object, mostly a subset of the [`Location`](location) for browsing scopes, but adapted to workers.

### Non-standard properties

 [`WorkerGlobalScope.performance`](workerglobalscope/performance) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the [`Performance`](performance) associated with the worker. It is a regular performance object, except that only a subset of its property and methods are available to workers.

 [`WorkerGlobalScope.console`](workerglobalscope/console) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the [`Console`](console) associated with the worker.

### Properties implemented from elsewhere

 [`WindowOrWorkerGlobalScope.caches`](windoworworkerglobalscope/caches) <span class="badge inline readonly">Read only </span>   
Returns the [`CacheStorage`](cachestorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

 [`WindowOrWorkerGlobalScope.indexedDB`](windoworworkerglobalscope/indexeddb) <span class="badge inline readonly">Read only </span>   
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; returns an [`IDBFactory`](idbfactory) object.

 [`WindowOrWorkerGlobalScope.isSecureContext`](windoworworkerglobalscope/issecurecontext) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the current context is secure (`true`) or not (`false`).

 [`WindowOrWorkerGlobalScope.origin`](windoworworkerglobalscope/origin) <span class="badge inline readonly">Read only </span>   
Returns the global object's origin, serialized as a string. (This does not yet appear to be implemented in any browser.)

Events
------

`error`  
Fired when an error occurred.  
Also available via the [`WorkerGlobalScope.onerror`](workerglobalscope/onerror) property.

`offline`  
Fired when the browser has lost access to the network and the value of `navigator.onLine` switched to `false`.  
Also available via the [`WorkerGlobalScope.onoffline`](workerglobalscope/onoffline) property.

`online`  
Fired when the browser has gained access to the network and the value of `navigator.onLine` switched to `true`.  
Also available via the [`WorkerGlobalScope.ononline`](workerglobalscope/ononline) property.

`languagechange`  
Fired at the global/worker scope object when the user's preferred languages change.  
Also available via the [`WorkerGlobalScope.onlanguagechange`](workerglobalscope/onlanguagechange) property.

 `close` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `close` event is raised.  
Also available via the [`WorkerGlobalScope.onclose`](workerglobalscope/onclose) property.

 `rejectionhandled` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
An event handler for handled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejection events.  
Also available via the <span class="page-not-created">`WorkerGlobalScope.onrejectionhandled`</span> property.

 `unhandledrejection` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
An event handler for unhandled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejection events.  
Also available via the <span class="page-not-created">`WorkerGlobalScope.onunhandledrejection`</span> property.

Methods
-------

*This interface inherits methods from the [`EventTarget`](eventtarget) interface and [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) and [`WindowEventHandlers`](windoweventhandlers) mixins.*

### Standard methods

[`WorkerGlobalScope.importScripts()`](workerglobalscope/importscripts)  
Imports one or more scripts into the worker's scope. You can specify as many as you'd like, separated by commas. For example:` importScripts('foo.js', 'bar.js');`

### Non-standard methods

 [`WorkerGlobalScope.dump()`](workerglobalscope/dump) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Allows you to write a message to stdout — i.e. in your terminal. This is the same as Firefox's [`window.dump`](window/dump), but for workers.

### Methods implemented from elsewhere

[`WindowOrWorkerGlobalScope.atob()`](windoworworkerglobalscope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa()`](windoworworkerglobalscope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval()`](windoworworkerglobalscope/clearinterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval).

[`WindowOrWorkerGlobalScope.clearTimeout()`](windoworworkerglobalscope/cleartimeout)  
Cancels the delayed execution set using [`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout).

[`WindowOrWorkerGlobalScope.createImageBitmap()`](windoworworkerglobalscope/createimagebitmap)  
Accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](imagebitmap). Optionally the source is cropped to the rectangle of pixels originating at *(sx, sy)* with width sw, and height sh.

[`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch)  
Starts the process of fetching a resource from the network.

[`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval)  
Schedules a function to execute every time a given number of milliseconds elapses.

[`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout)  
Schedules a function to execute in a given amount of time.

### Deprecated methods

[`WorkerGlobalScope.close()`](workerglobalscope/close)  
Discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope. In newer browser versions, `close()` is available on `DedicatedWorkerGlobalScope` and [`SharedWorkerGlobalScope`](sharedworkerglobalscope/close) instead. This change was made to stop `close()` being available on service workers, as it isn't supposed to be used there and always throws an exception when called (see [bug 1336043](https://bugzilla.mozilla.org/show_bug.cgi?id=1336043)).

Example
-------

You won't access `WorkerGlobalScope` directly in your code; however, its properties and methods are inherited by more specific global scopes such as [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope) and [`SharedWorkerGlobalScope`](sharedworkerglobalscope). For example, you could import another script into the worker and print out the contents of the worker scope's `navigator` object using the following two lines:

    importScripts('foo.js');
    console.log(navigator);

Since the global scope of the worker script is effectively the global scope of the worker you are running ([`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope) or whatever) and all worker global scopes inherit methods, properties, etc. from `WorkerGlobalScope`, you can run lines such as those above without specifying a parent object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#workerglobalscope">HTML Living Standard<br />
<span class="small">The definition of 'WorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`WorkerGlobalScope`

4

12

3.5

10

10.6

4

≤37

Yes

4

11

3.2

Yes

`dump`

No

No

No

No

No

No

No

No

4

No

No

No

`importScripts`

4

12

4

10

10.6

4

≤37

18

4

11

3.2

1.0

`languagechange_event`

4

12

74

Yes

11.5

4

≤37

40

No

Yes

5.1

4.0

`location`

4

12

3.5

Yes

11.5

4

37

40

4

Yes

5.1

4.0

`navigator`

4

17

3.5

Yes

11.5

4

37

40

4

Yes

5.1

4.0

`onclose`

4

12

3.5-50

Yes

11.5

4

37

40

4-50

Yes

5.1

4.0

`onerror`

4

12

3.5

Yes

11.5

4

37

40

4

Yes

5.1

4.0

`onlanguagechange`

4

12

74

Yes

11.5

4

37

40

No

Yes

5.1

4.0

`onoffline`

4

≤79

29

No

?

Yes

40

40

29

?

Yes

4.0

`ononline`

4

≤79

29

No

?

Yes

40

40

29

?

Yes

4.0

`performance`

Yes

≤79

34

No

?

Yes

Yes

Yes

34

?

Yes

Yes

`self`

4

12

3.5

Yes

11.5

4

37

40

34

Yes

5.1

4.0

See also
--------

-   Other global object interface: [`Window`](window), [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope), [`SharedWorkerGlobalScope`](sharedworkerglobalscope), , [`ServiceWorkerGlobalScope`](serviceworkerglobalscope)
-   Other Worker-related interfaces: [`Worker`](worker), [`WorkerLocation`](workerlocation), [`WorkerGlobalScope`](workerglobalscope), and [`ServiceWorkerGlobalScope`](serviceworkerglobalscope).
-   [Using web workers.](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope</a>
