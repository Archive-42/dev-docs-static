Worker
======

The `Worker` interface of the [Web Workers API](web_workers_api) represents a background task that can be created via script, which can send messages back to its creator. Creating a worker is done by calling the `Worker("path/to/worker/script")` constructor.

Workers may themselves spawn new workers, as long as those workers are hosted at the same [origin](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy) as the parent page. (Note: [nested workers are not yet implemented in WebKit](https://bugs.webkit.org/show_bug.cgi?id=22723)).

[Not all interfaces and functions are available](web_workers_api/functions_and_classes_available_to_workers) to scripts inside a `Worker`. Workers may use [`XMLHttpRequest`](xmlhttprequest) for network communication, but its `responseXML` and `channel` attributes are always `null`. (`fetch` is also available, with no such restrictions.)

Constructors
------------

[`Worker()`](worker/worker)  
Creates a dedicated web worker that executes the script at the specified URL. This also works for [Blob URLs](blob).

Properties
----------

*Inherits properties from its parent, [`EventTarget`](eventtarget), and implements properties from [`AbstractWorker`](abstractworker).*

### Event handlers

[`AbstractWorker.onerror`](abstractworker/onerror)  
An [`EventListener`](eventlistener) called whenever an [`ErrorEvent`](errorevent) of type `error` bubbles through to the worker. This is inherited from [`AbstractWorker`](abstractworker).

[`Worker.onmessage`](worker/onmessage)  
An [`EventListener`](eventlistener) called whenever a [`MessageEvent`](messageevent) of type `message` bubbles through the worker — i.e. when a message is sent to the parent document from the worker via [`DedicatedWorkerGlobalScope.postMessage`](dedicatedworkerglobalscope/postmessage). The message is stored in the event's [`data`](messageevent/data) property.

[`Worker.onmessageerror`](worker/onmessageerror)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `messageerror` event is raised.

Methods
-------

*Inherits methods from its parent, [`EventTarget`](eventtarget), and implements methods from [`AbstractWorker`](abstractworker).*

[`Worker.postMessage()`](worker/postmessage)  
Sends a message — consisting of any JavaScript object — to the worker's inner scope.

[`Worker.terminate()`](worker/terminate)  
Immediately terminates the worker. This does not let worker finish its operations; it is halted at once. `ServiceWorker` instances do not support this method.

Events
------

`message`  
Fires when the worker's parent receives a message from that worker.  
Also available via the `onmessage` property.

`messageerror`  
Fires when a `Worker` object receives a message that can't be [deserialized](web_workers_api/structured_clone_algorithm).  
Also available via the `onmessageerror` property.

`rejectionhandled`  
Fires every time a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejects, regardless of whether or not there is a handler to catch the rejection.  
Also available through the `onrejectionhandled` event handler property.

`unhandledrejection`  
Fires when a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejects with no handler to catch the rejection.  
Also available using the `onunhandledrejection` event handler property.

Example
-------

The following code snippet creates a [`Worker`](worker) object using the [`Worker()`](worker/worker) constructor, then uses the worker object:

    var myWorker = new Worker('/worker.js');
    var first = document.querySelector('input#number1');
    var second = document.querySelector('input#number2');

    first.onchange = function() {
      myWorker.postMessage([first.value, second.value]);
      console.log('Message posted to worker');
    }

For a full example, see our [Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#worker">HTML Living Standard<br />
<span class="small">The definition of 'Worker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Worker`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

`Worker`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

`message_event`

4

12

3.5

10

10.6

4

4

18

4

11.5

5.1

1.0

`messageerror_event`

60

18

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

`onmessage`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

`onmessageerror`

60

18

57

No

47

?

60

60

57

44

?

8.0

`postMessage`

Yes

12

Yes

10

Internet Explorer does not support `Transferable` objects.

47

Yes

Yes

Yes

Yes

44

Yes

Yes

`terminate`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

Support varies for different types of workers. See each worker type's page for specifics.

### Cross-origin worker error behavior

In early versions of the spec, loading a cross-origin worker script threw a `SecurityError`. Nowadays, an `error` event is thrown instead. Find out how to deal with this in *[Loading cross-origin worker now fires error event instead of throwing; worker in sandboxed iframe no longer allowed](https://github.com/mdn/kuma/issues/7647)*.

See also
--------

-   <a href="web_workers_api/using_web_workers" class="internal">Using Web Workers</a>
-   [Functions and classes available to Web Workers](web_workers_api/functions_and_classes_available_to_workers)
-   Other kind of workers: [`SharedWorker`](sharedworker) and [Service Worker](service_worker_api).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker</a>
