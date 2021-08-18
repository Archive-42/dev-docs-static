# DedicatedWorkerGlobalScope.onmessage

The `onmessage` property of the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `message` event occurs and bubbles through the [`Worker`](../worker) — i.e. when a message is sent to the worker using the [`Worker.postMessage`](../worker/postmessage) method.

## Syntax

    self.onmessage = function() { ... };

## Example

The following code snippet shows creation of a [`Worker`](../worker) object using the [`Worker()`](../worker/worker) constructor. Messages are passed to the worker when the value inside the form input `first` changes. A [`Worker.onmessage`](../worker/onmessage) handler is also present, to deal with messages are passed back from the worker.

    var myWorker = new Worker("worker.js");

    first.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
    }

In the `worker.js` script, a `DedicatedWorkerGlobalScope.onmessage` handler is used to handle messages from the main script:

    onmessage = function(e) {
      console.log('Message received from main script');
      var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
      console.log('Posting message back to main script');
      postMessage(workerResult);
    }

Notice how in the main script, `onmessage` has to be called on `myWorker`, whereas inside the worker script you just need `onmessage` because the worker is effectively the global scope (the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope), in this case).

For a full example, see our[Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-dedicatedworkerglobalscope-onmessage">HTML Living Standard<br />
<span class="small">The definition of 'DedicatedWorkerGlobalScope.onmessage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- The [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface it belongs to.
- [`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/onmessage</a>
