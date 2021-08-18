# CloseEvent()

The `CloseEvent()` constructor creates a new [`CloseEvent`](../closeevent).

## Syntax

    var event = new CloseEvent(typeArg, closeEventInit);

### Values

`typeArg`  
Is a [`DOMString`](../domstring) representing the name of the event.

`closeEventInit` <span class="badge inline optional">Optional</span>  
Is a `CloseEventInit` dictionary, having the following fields:

- `"wasClean"`, optional and defaulting to `false`, of type `long`, indicates if the connection has been closed cleanly or not.
- `"code"`, optional and defaulting to `0`, of type `unsigned short`, that is the connection close code sent by the server.
- `"reason"`, optional and defaulting to `''`, of type [`DOMString`](../domstring), that is a human-readable reason why the server closed the connection.

The `CloseEventInit` dictionary also accepts fields from the [`EventInit`](../event/event) dictionary.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#closeevent">HTML Living Standard<br />
<span class="small">The definition of 'CloseEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CloseEvent`

?

?

8

?

?

Yes

?

?

8

?

Yes

?

## See also

- [`CloseEvent`](../closeevent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent/CloseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent/CloseEvent</a>
