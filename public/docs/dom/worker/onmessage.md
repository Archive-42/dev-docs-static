Worker.onmessage
================

The `onmessage` property of the [`Worker`](../worker) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers), that is a function to be called when the `message` event occurs. These events are of type [`MessageEvent`](../messageevent) and will be called when the worker's parent receives a message (i.e. from the [`DedicatedWorkerGlobalScope.postMessage`](../dedicatedworkerglobalscope/postmessage) method).

Note that deserializing the message sent by [`postMessage()`](../dedicatedworkerglobalscope/postmessage) blocks the thread receiving it.

**Note**: The message payload is available in the `message` event's `data` property.

Syntax
------

    myWorker.onmessage = function(e) { ... }

Example
-------

The following code snippet shows creation of a [`Worker`](../worker) object using the [`Worker()`](worker) constructor. Messages are passed to the worker when the value inside the form input `first` changes. An onmessage handler is also present, to deal with messages that are passed back from the worker.

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
    }

In the `worker.js` script, an `onmessage` handler is used to the handle messages from the main script:

    onmessage = function(e) {
      console.log('Message received from main script');
      var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
      console.log('Posting message back to main script');
      postMessage(workerResult);
    }

Notice how in the main script, `onmessage` has to be called on `myWorker`, whereas inside the worker script you just need `onmessage` because the worker is effectively the global scope ([`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope)).

For a full example, see our[Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-worker-onmessage">HTML Living Standard<br />
<span class="small">The definition of 'Worker.onmessage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

See also
--------

The [`Worker`](../worker) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker/onmessage</a>
