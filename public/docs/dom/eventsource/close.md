# EventSource.close()

The `close()` method of the [`EventSource`](../eventsource) interface closes the connection, if one is made, and sets the [`EventSource.readyState`](readystate) attribute to `2` (closed).

**Note**: If the connection is already closed, the method does nothing.

## Syntax

    eventSource.close();

### Parameters

None.

### Return value

Void.

## Examples

    var button = document.querySelector('button');
    var evtSource = new EventSource('sse.php');

    button.onclick = function() {
      console.log('Connection closed');
      evtSource.close();
    }

**Note**: You can find a full example on GitHub — see [Simple SSE demo using PHP.](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-eventsource-close">HTML Living Standard<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`close`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventSource/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventSource/close</a>
