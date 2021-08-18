EventSource: open event
=======================

The `open` event of the [`EventSource`](../eventsource) API is fired when a connection with an event source is opened.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onopen"><code>EventSource.onopen</code></a></td></tr></tbody></table>

Examples
--------

    var evtSource = new EventSource('sse.php');

    // addEventListener version
    evtSource.addEventListener('open', (e) => {
      console.log("The connection has been established.");
    });

    // onopen version
    evtSource.onopen = (e) => {
      console.log("The connection has been established.");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-open">HTML Living Standard<br />
<span class="small">The definition of 'open event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`open_event`

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
-   `message`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/open_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/open_event</a>
