EventSource.readyState
======================

The `readyState` read-only property of the [`EventSource`](../eventsource) interface returns a number representing the state of the connection.

Syntax
------

    var myReadyState = eventSource.readyState;

### Value

A number representing the state of the connection. Possible values are:

-   `0` — connecting
-   `1` — open
-   `2` — closed

Examples
--------

    var evtSource = new EventSource('sse.php');
    console.log(evtSource.readyState);

**Note**: You can find a full example on GitHub — see [Simple SSE demo using PHP.](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-eventsource-readystate">HTML Living Standard<br />
<span class="small">The definition of 'readyState' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`readyState`

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

-   [`EventSource`](../eventsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/readyState</a>
