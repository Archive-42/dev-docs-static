MessageEvent
============

The `MessageEvent` interface represents a message received by a target object.

This is used to represent messages in:

-   [Server-sent events](server-sent_events) (see [`EventSource.onmessage`](eventsource/onmessage)).
-   [Web sockets](websockets_api) (see the `onmessage` property of the [WebSocket](websocket) interface).
-   Cross-document messaging (see [`Window.postMessage()`](window/postmessage) and <span class="page-not-created">`Window.onmessage`</span>).
-   [Channel messaging](channel_messaging_api) (see [`MessagePort.postMessage()`](messageport/postmessage) and [`MessagePort.onmessage`](messageport/onmessage)).
-   Cross-worker/document messaging (see the above two entries, but also [`Worker.postMessage()`](worker/postmessage), [`Worker.onmessage`](worker/onmessage), [`ServiceWorkerGlobalScope.onmessage`](serviceworkerglobalscope/onmessage), etc.)
-   [Broadcast channels](broadcast_channel_api) (see [`Broadcastchannel.postMessage()`](broadcastchannel/postmessage)) and [`BroadcastChannel.onmessage`](broadcastchannel/onmessage)).
-   WebRTC data channels (see [`RTCDataChannel.onmessage`](rtcdatachannel/onmessage)).

The action triggered by this event is defined in a function set as the event handler for the relevant `message` event (e.g. using an `onmessage` handler as listed above).

**Note:** This feature is available in [Web Workers](web_workers_api).

  

Constructor
-----------

[`MessageEvent()`](messageevent/messageevent)  
Creates a new `MessageEvent`.

Properties
----------

*This interface also inherits properties from its parent, [`Event`](event).*

 [`MessageEvent.data`](messageevent/data) <span class="badge inline readonly">Read only </span>   
The data sent by the message emitter.

 [`MessageEvent.origin`](messageevent/origin) <span class="badge inline readonly">Read only </span>   
A [`USVString`](usvstring) representing the origin of the message emitter.

 [`MessageEvent.lastEventId`](messageevent/lasteventid) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing a unique ID for the event.

 [`MessageEvent.source`](messageevent/source) <span class="badge inline readonly">Read only </span>   
A `MessageEventSource` (which can be a <span class="page-not-created">`WindowProxy`</span>, [`MessagePort`](messageport), or [`ServiceWorker`](serviceworker) object) representing the message emitter.

 [`MessageEvent.ports`](messageevent/ports) <span class="badge inline readonly">Read only </span>   
An array of [`MessagePort`](messageport) objects representing the ports associated with the channel the message is being sent through (where appropriate, e.g. in channel messaging or when sending a message to a shared worker).

Methods
-------

*This interface also inherits methods from its parent, [`Event`](event).*

 <span class="page-not-created">`initMessageEvent()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Initializes a message event. **Do not use this anymore** — **use the [`MessageEvent()`](messageevent/messageevent) constructor instead.**

Examples
--------

In our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/)), we have two HTML pages, each of which uses some JavaScript to perform a simple calculation. The different scripts are using the same worker file to perform the calculation — they can both access it, even if their pages are running inside different windows.

The following code snippet shows creation of a [`SharedWorker`](sharedworker) object using the [`SharedWorker()`](sharedworker/sharedworker) constructor. Both scripts contain this:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#messageevent">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MessageEvent`

1

12

4

9

10.6

4

1

18

4

11

3

1.0

`MessageEvent`

1

12

4

9

?

4

37

18

?

?

3

1.0

`data`

1

12

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

`initMessageEvent`

1

12

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

`lastEventId`

1

17

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

`origin`

1

12

4

9

Yes

4

1

Yes

4

Yes

3

Yes

`ports`

1

12

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

`source`

Yes

12

55

No

Yes

Yes

Yes

Yes

55

Yes

Yes

Yes

See also
--------

-   [`ExtendableMessageEvent`](extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent</a>
