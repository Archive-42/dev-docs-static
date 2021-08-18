# DedicatedWorkerGlobalScope.postMessage()

The `postMessage()` method of the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface sends a message to the main thread that spawned it. This accepts a single parameter, which is the data to send to the worker. The data may be any value or JavaScript object handled by the [structured clone](../web_workers_api/structured_clone_algorithm) algorithm, which includes cyclical references.

The main scope that spawned the worker can send back information to the thread that spawned it using the [`Worker.postMessage`](../worker/postmessage) method.

## Syntax

    postMessage(aMessage, transferList);

### Parameters

_aMessage_  
The object to deliver to the main thread; this will be in the data field in the event delivered to the [`Worker.onmessage`](../worker/onmessage) handler. This may be any value or JavaScript object handled by the [structured clone](../web_workers_api/structured_clone_algorithm) algorithm, which includes cyclical references.

_transferList_ <span class="badge inline optional">Optional</span>  
An optional [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Transferable`](../transferable) objects to transfer ownership of. If the ownership of an object is transferred, it becomes unusable in the context it was sent from and it becomes available only to the main thread it was sent to.

Only [`MessagePort`](../messageport) and [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects can be transferred.

### Returns

Void.

## Example

The following code snippet shows `worker.js`, in which an `onmessage` handler is used to handle messages from the main script. Inside the handler a calculation is done from which a result message is created; this is then sent back to the main thread using `postMessage(workerResult);`

    onmessage = function(e) {
      console.log('Message received from main script');
      var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
      console.log('Posting message back to main script');
      postMessage(workerResult);
    }

In the main script, `onmessage` would have to be called on a `Worker object`, whereas inside the worker script you just need `onmessage` because the worker is effectively the global scope ([`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope)).

For a full example, see our[Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).

**Note**: `postMessage()` can only send a single object at once. As seen above, if you want to pass multiple values you can send an array.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-dedicatedworkerglobalscope-postmessage">HTML Living Standard<br />
<span class="small">The definition of 'DedicatedWorkerGlobalScope.postMessage()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

The [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/postMessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/postMessage</a>
