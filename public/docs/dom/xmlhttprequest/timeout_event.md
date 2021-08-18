XMLHttpRequest: timeout event
=============================

The `timeout` event is fired when progression is terminated due to preset time expiring.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../progressevent"><code>ProgressEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>XMLHttpRequestEventTarget.ontimeout</code></span></td></tr></tbody></table>

Examples
--------

    const client = new XMLHttpRequest();
    client.open('GET', 'http://www.example.org/example.txt');
    client.ontimeout = () => {
        console.error('Timeout!!')
    };

    client.send();

You could also set up the event handler using the [`addEventListener()`](../eventtarget/addeventlistener) method:

    client.addEventListener('timeout', () => {
        console.error("Timeout!!");
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#event-xhr-timeout">XMLHttpRequest<br />
<span class="small">The definition of 'timeout event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`timeout_event`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`XMLHttpRequest`](../xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout_event</a>
