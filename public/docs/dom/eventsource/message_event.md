EventSource: message event
==========================

The `message` event of the [`EventSource`](../eventsource) API is fired when data is received through an event source.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onmessage"><code>EventSource.onmessage</code></a></td></tr></tbody></table>

Examples
--------

In this basic example, an `EventSource` is created to receive events from the server; a page with the name `sse.php` is responsible for generating the events.

    var evtSource = new EventSource('sse.php');
    var eventList = document.querySelector('ul');

    evtSource.addEventListener('message', (e) => {
      var newElement = document.createElement("li");

      newElement.textContent = "message: " + e.data;
      eventList.appendChild(newElement);
    });

### onmessage equivalent

    evtSource.onmessage = (e) => {
      var newElement = document.createElement("li");

      newElement.textContent = "message: " + e.data;
      eventList.appendChild(newElement);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-message">HTML Living Standard<br />
<span class="small">The definition of 'message event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`message_event`

6

79

6

No

Yes

5

≤37

18

45

12

5

1.0

See also
--------

-   [Using server-sent events](../server-sent_events/using_server-sent_events)
-   `open`
-   `error`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/message_event</a>
