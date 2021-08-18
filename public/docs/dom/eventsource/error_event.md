EventSource: error event
========================

The `error` event of the [`EventSource`](../eventsource) API is fired when a connection with an event source fails to be opened.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a> or <a href="../errorevent"><code>ErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onerror"><code>EventSource.onerror</code></a></td></tr></tbody></table>

Examples
--------

    var evtSource = new EventSource('sse.php');

    // addEventListener version
    evtSource.addEventListener('error', (e) => {
      console.log("An error occurred while attempting to connect.");
    });

    // onerror version
    evtSource.onerror = (e) => {
      console.log("An error occurred while attempting to connect.");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-error">HTML Living Standard<br />
<span class="small">The definition of 'error event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`error_event`

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
-   `message`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/error_event</a>
