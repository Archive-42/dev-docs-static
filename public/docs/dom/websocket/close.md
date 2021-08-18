WebSocket.close()
=================

The `WebSocket.close()` method closes the [`WebSocket`](../websocket) connection or connection attempt, if any. If the connection is already `CLOSED`, this method does nothing.

Syntax
------

    WebSocket.close();

    WebSocket.close(code);

    WebSocket.close(reason);

    WebSocket.close(code, reason);

### Parameters

 `code` <span class="badge inline optional">Optional</span>   
A numeric value indicating the status code explaining why the connection is being closed. If this parameter is not specified, a default value of 1005 is assumed. See the [list of status codes](../closeevent#status_codes) of [`CloseEvent`](../closeevent) for permitted values.

 `reason` <span class="badge inline optional">Optional</span>   
A human-readable string explaining why the connection is closing. This string must be no longer than 123 bytes of UTF-8 text (**not** characters).

### Exceptions thrown

`INVALID_ACCESS_ERR`  
An invalid `code` was specified.

`SYNTAX_ERR`  
The `reason` string is too long or contains unpaired surrogates.

**Note:** In Gecko, this method didn't support any parameters prior to Gecko 8.0 (Firefox 8.0 / Thunderbird 8.0 / SeaMonkey 2.5).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-sockets.html#dom-websocket-close">HTML Living Standard<br />
<span class="small">The definition of 'WebSocket.close()' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`close`

4

12

8

4-8

Parameters not supported, see [bug 674716](https://bugzil.la/674716).

10

12.1

5

≤37

18

8

4-8

Parameters not supported, see [bug 674716](https://bugzil.la/674716).

12.1

4.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/close</a>
