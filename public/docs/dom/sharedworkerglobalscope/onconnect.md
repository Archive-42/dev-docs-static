SharedWorkerGlobalScope.onconnect
=================================

The `onconnect` property of the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) interface is an event handler representing the code to be called when the `connect` event is raised — that is, when a [`MessagePort`](../messageport) connection is opened between the associated [`SharedWorker`](../sharedworker) and the main thread.

Syntax
------

    onconnect = function() { ... };

Examples
--------

This example shows a shared worker file — when a connection to the worker occurs from a main thread via a [`MessagePort`](../messageport), the `onconnect` event handler fires. The event object is a [`MessageEvent`](../messageevent).

The connecting port can be referenced through the event object's `ports` parameter; this reference can have an `onmessage` handler attached to it to handle messages coming in through the port, and its `postMessage()` method can be used to send messages back to the main thread using the worker.

    onconnect = function(e) {
        var port = e.ports[0];

        port.onmessage = function(e) {
          var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
          port.postMessage(workerResult);
        }

        port.start();
    }

For a complete running example, see our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/).)

**Note**: The `data` property of the event object used to be `null` in Firefox. As of version 65 it is now initialized to an empty string, as per spec ([bug 1508824](https://bugzilla.mozilla.org/show_bug.cgi?id=1508824)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-sharedworkerglobalscope-onconnect">HTML Living Standard<br />
<span class="small">The definition of 'onconnect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

-   [`SharedWorkerGlobalScope`](../sharedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/onconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/onconnect</a>
