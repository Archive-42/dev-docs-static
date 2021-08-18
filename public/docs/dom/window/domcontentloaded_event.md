Window: DOMContentLoaded event
==============================

The `DOMContentLoaded` event fires when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes (although specified as a simple event that isn't cancelable)</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td>None</td></tr></tbody></table>

The original target for this event is the [`Document`](../document) that has loaded. You can listen for this event on the `Window` interface to handle it in the capture or bubbling phases. For full details on this event please see the page on the Document: [`DOMContentLoaded`](../document/domcontentloaded_event) event.

A different event, [`load`](load_event), should be used only to detect a fully-loaded page. It is a common mistake to use `load` where `DOMContentLoaded` would be more appropriate.

Examples
--------

### Basic usage

    window.addEventListener('DOMContentLoaded', (event) => {
        console.log('DOM fully loaded and parsed');
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-domcontentloaded">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`DOMContentLoaded_event`

1

12

1

9

9

3.1

1

18

4

10.1

2

1.0

See also
--------

-   Related events: [`load`](load_event), [`readystatechange`](../document/readystatechange_event), [`beforeunload`](beforeunload_event), [`unload`](unload_event)
-   This event on [`Document`](../document) targets: [`DOMContentLoaded`](../document/domcontentloaded_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/DOMContentLoaded_event</a>
