SharedWorkerGlobalScope: connect event
======================================

The `connect` event is fired in shared workers at their [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) when a new client connects.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onconnect"><code>SharedWorkerGlobalScope.onconnect</code></a></td></tr></tbody></table>

Examples
--------

This example shows a shared worker file — when a connection to the worker occurs from a main thread via a [`MessagePort`](../messageport), the `onconnect` event handler fires. The event object is a [`MessageEvent`](../messageevent).

The connecting port can be referenced through the event object's `ports` parameter; this reference can have an `onmessage` handler attached to it to handle messages coming in through the port, and its `postMessage()` method can be used to send messages back to the main thread using the worker.

    self.onconnect = function(e) {
        var port = e.ports[0];

        port.onmessage = function(e) {
          var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
          port.postMessage(workerResult);
        }

        port.start();
    }

For a complete running example, see our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/).)

### addEventListener equivalent

You could also set up an event handler using the [`addEventListener()`](../eventtarget/addeventlistener) method:

    self.addEventListener('connect', function(e) {
      var port = e.ports[0];

      port.onmessage = function(e) {
        var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
        port.postMessage(workerResult);
      }

    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-workerglobalscope-connect">HTML Living Standard<br />
<span class="small">The definition of 'connect event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

See also
--------

-   [Using web workers](../web_workers_api/using_web_workers)
-   [`SharedWorkerGlobalScope`](../sharedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/connect_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/connect_event</a>
