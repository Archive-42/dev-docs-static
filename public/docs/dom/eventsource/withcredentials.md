# EventSource.withCredentials

The `withCredentials` read-only property of the [`EventSource`](../eventsource) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `EventSource` object was instantiated with CORS credentials set.

## Syntax

    var myWithCredentials = eventSource.withCredentials;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `EventSource` object was instantiated with CORS credentials set (`true`), or not (`false`, the default).

## Examples

    var evtSource = new EventSource('sse.php');
    console.log(evtSource.withCredentials);

**Note**: You can find a full example on GitHub — see [Simple SSE demo using PHP.](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-eventsource-withcredentials">HTML Living Standard<br />
<span class="small">The definition of 'withCredentials' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`withCredentials`

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

## See also

- [`EventSource`](../eventsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/withCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/withCredentials</a>
