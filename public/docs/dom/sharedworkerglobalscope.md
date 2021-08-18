SharedWorkerGlobalScope
=======================

The `SharedWorkerGlobalScope` object (the [`SharedWorker`](sharedworker) global scope) is accessible through the [`self`](window/self) keyword. Some additional global functions, namespaces objects, and constructors, not typically associated with the worker global scope, but available on it, are listed in the [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference). See the complete list of [functions available to workers](web_workers_api/functions_and_classes_available_to_workers).

Properties
----------

*This interface inherits properties from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements properties from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers).*

 [`SharedWorkerGlobalScope.name`](sharedworkerglobalscope/name) <span class="badge inline readonly">Read only </span>   
The name that the [`SharedWorker`](sharedworker) was (optionally) given when it was created using the [`SharedWorker()`](sharedworker/sharedworker) constructor. This is mainly useful for debugging purposes.

 [`SharedWorkerGlobalScope.applicationCache`](sharedworkerglobalscope/applicationcache) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This property returns the <span class="page-not-created">`ApplicationCache`</span> object for the worker (see [Using the application cache](https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache)).

### Properties inherited from WorkerGlobalScope

[`WorkerGlobalScope.self`](workerglobalscope/self)  
Returns an object reference to the `DedicatedWorkerGlobalScope` object itself.

 [`WorkerGlobalScope.console`](workerglobalscope/console) <span class="badge inline readonly">Read only </span>   
Returns the [`Console`](console) associated with the worker.

 [`WorkerGlobalScope.location`](workerglobalscope/location) <span class="badge inline readonly">Read only </span>   
Returns the [`WorkerLocation`](workerlocation) associated with the worker. `WorkerLocation` is a specific location object, mostly a subset of the [`Location`](location) for browsing scopes, but adapted to workers.

 [`WorkerGlobalScope.navigator`](workerglobalscope/navigator) <span class="badge inline readonly">Read only </span>   
Returns the [`WorkerNavigator`](workernavigator) associated with the worker. `WorkerNavigator` is a specific navigator object, mostly a subset of the [`Navigator`](navigator) for browsing scopes, but adapted to workers.

 [`WorkerGlobalScope.performance`](workerglobalscope/performance) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the [`Performance`](performance) object associated with the worker, which is a regular performance object, but with a subset of its properties and methods available.

### Event handlers

*This interface inherits event handlers from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements event handlers from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers).*

[`SharedWorkerGlobalScope.onconnect`](sharedworkerglobalscope/onconnect)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `connect` event is raised — that is, when a [`MessagePort`](messageport) connection is opened between the associated [`SharedWorker`](sharedworker) and the main thread.

Methods
-------

*This interface inherits methods from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements methods from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers).*

[`SharedWorkerGlobalScope.close()`](sharedworkerglobalscope/close)  
Discards any tasks queued in the `SharedWorkerGlobalScope`'s event loop, effectively closing this particular scope.

### Inherited from WorkerGlobalScope

 [`WorkerGlobalScope.close()`](workerglobalscope/close) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope.

 [`WorkerGlobalScope.dump()`](workerglobalscope/dump) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Allows you to write a message to stdout — i.e. in your terminal. This is the same as Firefox's [`window.dump`](window/dump), but for workers.

[`WorkerGlobalScope.importScripts()`](workerglobalscope/importscripts)  
Imports one or more scripts into the worker's scope. You can specify as many as you'd like, separated by commas. For example:` importScripts('foo.js', 'bar.js');`

### Implemented from other places

[`WindowBase64.atob()`](windoworworkerglobalscope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowBase64.btoa()`](windoworworkerglobalscope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowTimers.clearInterval()`](windoworworkerglobalscope/clearinterval)  
Cancels the repeated execution set using [`WindowTimers.setInterval()`](windoworworkerglobalscope/setinterval).

[`WindowTimers.clearTimeout()`](windoworworkerglobalscope/cleartimeout)  
Cancels the repeated execution set using [`WindowTimers.setTimeout()`](windoworworkerglobalscope/settimeout).

[`WindowTimers.setInterval()`](windoworworkerglobalscope/setinterval)  
Schedules the execution of a function every X milliseconds.

[`WindowTimers.setTimeout()`](windoworworkerglobalscope/settimeout)  
Sets a delay for executing a function.

Events
------

Listen to this event using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`connect`  
Fired on shared workers when a new client connects.  
Also available via the `onconnect` property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#sharedworkerglobalscope">HTML Living Standard<br />
<span class="small">The definition of 'SharedWorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`SharedWorkerGlobalScope`

4

79

29

No

10.6

5

Yes

Yes

4

11

7

Yes

`applicationCache`

4

79

29

No

10.6

No

Yes

Yes

29

Yes

?

Yes

`close`

4

79

29

No

11.5

5

≤37

18

29

11

7

1.0

`connect_event`

4

79

29

Before version 65 the `data` property of the event object was `null`; it is now initialized to an empty string, as per spec.

No

10.6

No

Yes

18

29

Before version 65 the `data` property of the event object was `null`; it is now initialized to an empty string, as per spec.

Yes

?

1.0

`name`

Yes

79

55

No

10.6

No

Yes

40

55

Yes

No

4.0

`onconnect`

4

79

29

No

10.6

No

Yes

18

29

Yes

?

1.0

See also
--------

-   [`SharedWorker`](sharedworker)
-   [`WorkerGlobalScope`](workerglobalscope)
-   [Using Web workers](web_workers_api/using_web_workers)
-   [Functions available to workers](web_workers_api/functions_and_classes_available_to_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope</a>
