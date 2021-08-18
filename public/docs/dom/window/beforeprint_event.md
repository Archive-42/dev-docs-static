Window: beforeprint event
=========================

The `beforeprint` event is fired when the associated document is about to be printed or previewed for printing.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onbeforeprint"><code>onbeforeprint</code></a></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    window.addEventListener('beforeprint', (event) => {
      console.log('Before print');
    });

Using the `onbeforeprint` event handler property:

    window.onbeforeprint = (event) => {
      console.log('Before print');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#event-beforeprint">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`beforeprint_event`

63

12

6

Yes

50

13

63

63

?

46

13

8.0

See also
--------

-   Related events: [`afterprint`](afterprint_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeprint_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/beforeprint_event</a>
