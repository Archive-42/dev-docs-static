Window: offline event
=====================

The `offline` event of the [`Window`](../window) interface is fired when the browser has lost access to the network and the value of [`Navigator.onLine`](../navigatoronline/online) switches to `false`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onoffline</code></span></td></tr></tbody></table>

Examples
--------

    // addEventListener version
    window.addEventListener('offline', (event) => {
        console.log("The network connection has been lost.");
    });

    // onoffline version
    window.onoffline = (event) => {
      console.log("The network connection has been lost.");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-offline">HTML Living Standard<br />
<span class="small">The definition of 'offline event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`offline_event`

Yes

12

Yes

Yes

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

-   [`online`](online_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/offline_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/offline_event</a>
