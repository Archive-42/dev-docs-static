# EventSource()

The ` EventSource``() ` constructor returns a newly-created [`EventSource`](../eventsource), which represents a remote resource.

## Syntax

    eventSource = new EventSource(url, configuration);

### Parameters

`url`  
A [`USVString`](../usvstring) that represents the location of the remote resource serving the events/messages.

`configuration` <span class="badge inline optional">Optional</span>  
Provides options to configure the new connection. The possible entries are:

- `withCredentials`, defaulting to `false`, indicating if CORS should be set to `include` credentials.

## Examples

    var evtSource = new EventSource('sse.php');
    var eventList = document.querySelector('ul');

    evtSource.onmessage = function(e) {
      var newElement = document.createElement("li");

      newElement.textContent = "message: " + e.data;
      eventList.appendChild(newElement);
    }

**Note**: You can find a full example on GitHub — see [Simple SSE demo using PHP.](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-eventsource">HTML Living Standard<br />
<span class="small">The definition of 'EventSource()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`EventSource`

9

79

6

No

11

5

≤37

18

45

12

5

1.0

`cors_support`

26

79

11

No

12

?

≤37

26

45

12

?

2.0

## See also

- [`EventSource`](../eventsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/EventSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/EventSource</a>
