Window: messageerror event
==========================

The `messageerror` event is fired on a [`Window`](../window) object when it receives a message that can't be deserialized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onmessageerror"><code>onmessageerror</code></a></td></tr></tbody></table>

Examples
--------

Listen for `messageerror` using [`addEventListener()`](../eventtarget/addeventlistener):

    window.addEventListener('messageerror', (event) => {
        console.error(event);
    });

The same, but using the [`onmessageerror`](../windoweventhandlers/onmessageerror) event handler property:

    window.onmessageerror = (event) => {
        console.error(event);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-messageerror">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`messageerror_event`

60

≤79

57

?

47

?

60

60

57

47

?

8.0

See also
--------

-   [`Window.postMessage()`](postmessage)
-   Related events: [`message`](message_event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/messageerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/messageerror_event</a>
