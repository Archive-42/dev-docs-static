XMLHttpRequest.readyState
=========================

The **XMLHttpRequest.readyState** property returns the state an XMLHttpRequest client is in. An XHR client exists in one of the following states:

<table><thead><tr class="header"><th>Value</th><th>State</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td><code>UNSENT</code></td><td>Client has been created. <code>open()</code> not called yet.</td></tr><tr class="even"><td><code>1</code></td><td><code>OPENED</code></td><td><code>open()</code> has been called.</td></tr><tr class="odd"><td><code>2</code></td><td><code>HEADERS_RECEIVED</code></td><td><code>send()</code> has been called, and headers and status are available.</td></tr><tr class="even"><td><code>3</code></td><td><code>LOADING</code></td><td>Downloading; <code>responseText</code> holds partial data.</td></tr><tr class="odd"><td><code>4</code></td><td><code>DONE</code></td><td>The operation is complete.</td></tr></tbody></table>

UNSENT  
The XMLHttpRequest client has been created, but the open() method hasn't been called yet.

OPENED  
open() method has been invoked. During this state, the request headers can be set using the [setRequestHeader()](setrequestheader) method and the [send()](send) method can be called which will initiate the fetch.

HEADERS\_RECEIVED  
send() has been called and the response headers have been received.

LOADING  
Response's body is being received. If `responseType` is "text" or empty string, `responseText` will have the partial text response as it loads.

DONE  
The fetch operation is complete. This could mean that either the data transfer has been completed successfully or failed.

The state names are different in versions of Internet Explorer earlier than 11. Instead of `UNSENT`, `OPENED`,` HEADERS_RECEIVED`,` LOADING` and `DONE`, the names `READYSTATE_UNINITIALIZED` (0), `READYSTATE_LOADING` (1), `READYSTATE_LOADED` (2), `READYSTATE_INTERACTIVE` (3) and `READYSTATE_COMPLETE` (4) are used.

Example
-------

    var xhr = new XMLHttpRequest();
    console.log('UNSENT', xhr.readyState); // readyState will be 0

    xhr.open('GET', '/api', true);
    console.log('OPENED', xhr.readyState); // readyState will be 1

    xhr.onprogress = function () {
        console.log('LOADING', xhr.readyState); // readyState will be 3
    };

    xhr.onload = function () {
        console.log('DONE', xhr.readyState); // readyState will be 4
    };

    xhr.send(null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#states">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

1

12

1

7

8

1.2

1

18

4

10.1

1

1.0

`constants`

Yes

12

9

9

12

Yes

Yes

18

9

Yes

?

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState</a>
