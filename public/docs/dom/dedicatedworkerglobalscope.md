# DedicatedWorkerGlobalScope

The `DedicatedWorkerGlobalScope` object (the [`Worker`](worker) global scope) is accessible through the [`self`](window/self) keyword. Some additional global functions, namespaces objects, and constructors, not typically associated with the worker global scope, but available on it, are listed in the [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference). See also: [Functions available to workers](web_workers_api/functions_and_classes_available_to_workers).

## Properties

_This interface inherits properties from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements properties from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers)._

[`DedicatedWorkerGlobalScope.name`](dedicatedworkerglobalscope/name) <span class="badge inline readonly">Read only </span>  
The name that the [`Worker`](worker) was (optionally) given when it was created using the [`Worker()`](worker/worker) constructor. This is mainly useful for debugging purposes.

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

_This interface inherits event handlers from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements event handlers from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers)._

[`DedicatedWorkerGlobalScope.onmessage`](dedicatedworkerglobalscope/onmessage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `message` event is raised. These events are of type [`MessageEvent`](messageevent) and will be called when the worker receives a message from the document that started it (i.e. from the [`Worker.postMessage`](worker/postmessage) method.)

[`DedicatedWorkerGlobalScope.onmessageerror`](dedicatedworkerglobalscope/onmessageerror)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `messageerror` event is raised.

## Methods

_This interface inherits methods from the [`WorkerGlobalScope`](workerglobalscope) interface, and its parent [`EventTarget`](eventtarget), and therefore implements methods from [`WindowTimers`](windoworworkerglobalscope), [`WindowBase64`](windoworworkerglobalscope), and [`WindowEventHandlers`](windoweventhandlers)._

[`DedicatedWorkerGlobalScope.close()`](dedicatedworkerglobalscope/close)  
Discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope.

[`DedicatedWorkerGlobalScope.postMessage()`](dedicatedworkerglobalscope/postmessage)  
Sends a message — which can consist of `any` JavaScript object — to the parent document that first spawned the worker.

### Inherited from WorkerGlobalScope

[`WorkerGlobalScope.dump()`](workerglobalscope/dump) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Writes a message to the console.

[`WorkerGlobalScope.importScripts()`](workerglobalscope/importscripts)  
Imports one or more scripts into the worker's scope. You can specify as many as you'd like, separated by commas. For example:` importScripts('foo.js', 'bar.js');`

### Implemented from other places

[`WindowOrWorkerGlobalScope.atob`](windoworworkerglobalscope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa`](windoworworkerglobalscope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval`](windoworworkerglobalscope/clearinterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval`](windoworworkerglobalscope/setinterval).

[`WindowOrWorkerGlobalScope.clearTimeout`](windoworworkerglobalscope/cleartimeout)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setTimeout`](windoworworkerglobalscope/settimeout).

[`WindowOrWorkerGlobalScope.setInterval`](windoworworkerglobalscope/setinterval)  
Schedules the execution of a function every X milliseconds.

[`WindowOrWorkerGlobalScope.setTimeout`](windoworworkerglobalscope/settimeout)  
Sets a delay for executing a function.

## Events

`message`  
Fired when the worker receives a message from its parent.  
Also available via the `onmessage` property.

`messageerror`  
Fired when a worker receives a message that can't be deserialized.  
Also available via the `onmessageerror` property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dedicatedworkerglobalscope">HTML Living Standard<br />
<span class="small">The definition of 'DedicatedWorkerGlobalScope' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`DedicatedWorkerGlobalScope`

4

12

3.5

10

10.6

4

≤37

18

4

11

5.1

1.0

`close`

4

12

3.5

10

11.5

4

≤37

18

4

11.5

5.1

1.0

`message_event`

4

12

3.5

10

10.6

4

≤37

Yes

4

11.5

5.1

Yes

`messageerror_event`

60

≤79

57

?

47

?

60

60

57

47

?

8.0

`name`

Yes

18

55

No

?

12.1

Yes

Yes

55

?

12.2

Yes

`onmessage`

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

5.1

Yes

`onmessageerror`

60

18

57

?

47

?

60

60

57

44

?

8.0

`postMessage`

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

5.1

Yes

## See also

- [`Worker`](worker)
- [`WorkerGlobalScope`](workerglobalscope)
- [Using web workers](web_workers_api/using_web_workers)
- [Functions available to workers](web_workers_api/functions_and_classes_available_to_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope</a>
