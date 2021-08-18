SharedWorker
============

The `SharedWorker` interface represents a specific kind of worker that can be *accessed* from several browsing contexts, such as several windows, iframes or even workers. They implement an interface different than dedicated workers and have a different global scope, [`SharedWorkerGlobalScope`](sharedworkerglobalscope).

**Note:** If SharedWorker can be accessed from several browsing contexts, all those browsing contexts must share the exact same origin (same protocol, host and port).

Constructors
------------

[`SharedWorker()`](sharedworker/sharedworker)  
Creates a shared web worker that executes the script at the specified URL.

Properties
----------

*Inherits properties from its parent, [`EventTarget`](eventtarget), and implements properties from [`AbstractWorker`](abstractworker).*

[`AbstractWorker.onerror`](abstractworker/onerror)  
Is an [`EventListener`](eventlistener) that is called whenever an [`ErrorEvent`](errorevent) of type `error` bubbles through the worker.

 [`SharedWorker.port`](sharedworker/port) <span class="badge inline readonly">Read only </span>   
Returns a [`MessagePort`](messageport) object used to communicate with and control the shared worker.

Methods
-------

*Inherits methods from its parent, [`EventTarget`](eventtarget), and implements methods from [`AbstractWorker`](abstractworker).*

Example
-------

In our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/)), we have two HTML pages, each of which uses some JavaScript to perform a simple calculation. The different scripts are using the same worker file to perform the calculation — they can both access it, even if their pages are running inside different windows.

The following code snippet shows creation of a `SharedWorker` object using the [`SharedWorker()`](sharedworker/sharedworker) constructor. Both scripts contain this:

    var myWorker = new SharedWorker('worker.js');

Both scripts then access the worker through a [`MessagePort`](messageport) object created using the [`SharedWorker.port`](sharedworker/port) property. If the onmessage event is attached using addEventListener, the port is manually started using its `start()` method:

    myWorker.port.start();

When the port is started, both scripts post messages to the worker and handle messages sent from it using `port.postMessage()` and `port.onmessage`, respectively:

    first.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    second.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    myWorker.port.onmessage = function(e) {
      result1.textContent = e.data;
      console.log('Message received from worker');
    }

Inside the worker we use the [`SharedWorkerGlobalScope.onconnect`](sharedworkerglobalscope/onconnect) handler to connect to the same port discussed above. The ports associated with that worker are accessible in the `connect` event's `ports` property — we then use [`MessagePort`](messageport) `start()` method to start the port, and the `onmessage` handler to deal with messages sent from the main threads.

    onconnect = function(e) {
      var port = e.ports[0];

      port.addEventListener('message', function(e) {
        var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
        port.postMessage(workerResult);
      });

      port.start(); // Required when using addEventListener. Otherwise called implicitly by onmessage setter.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#sharedworker">HTML Living Standard<br />
<span class="small">The definition of 'SharedWorker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="about:unknown">Unknown</a>.</td></tr></tbody></table>

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

`SharedWorker`

4

79

29

No

10.6

5-6.1

No

No

33

11-14

5.1-7

4.0-5.0

`SharedWorker`

4

79

29

No

10.6

5-6.1

No

No

33

11-14

5.1-7

4.0-5.0

`port`

4

79

29

No

10.6

5-6.1

No

No

33

11-14

5.1-7

4.0-5.0

See also
--------

-   [`Worker`](worker)
-   <a href="web_workers_api/using_web_workers" class="internal">Using web workers</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker</a>
