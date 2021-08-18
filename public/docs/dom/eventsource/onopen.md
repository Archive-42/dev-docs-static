EventSource.onopen
==================

The `onopen` property of the [`EventSource`](../eventsource) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when an `open` event is received, that is when the connection was just opened.

Syntax
------

    eventSource.onopen = function

Examples
--------

    evtSource.onopen = function() {
      console.log("Connection to server opened.");
    };

**Note**: You can find a full example on GitHub — see [Simple SSE demo using PHP.](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#handler-eventsource-onopen">HTML Living Standard<br />
<span class="small">The definition of 'onopen' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onopen`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/onopen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/onopen</a>
