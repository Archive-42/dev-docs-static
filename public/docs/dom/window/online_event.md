Window: online event
====================

The `online` event of the [`Window`](../window) interface is fired when the browser has gained access to the network and the value of [`Navigator.onLine`](../navigatoronline/online) switches to `true`.

**Note:** This event shouldn't be used to determine the availability of a particular website. Network problems or firewalls might still prevent the website from being reached.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>ononline</code></span></td></tr></tbody></table>

Examples
--------

    // addEventListener version
    window.addEventListener('online', (event) => {
        console.log("You are now connected to the network.");
    });

    // ononline version
    window.ononline = (event) => {
      console.log("You are now connected to the network.");
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-online">HTML Living Standard<br />
<span class="small">The definition of 'online event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`online_event`

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

-   [`offline`](offline_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/online_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/online_event</a>
