Window: afterprint event
========================

The `afterprint` event is fired after the associated document has started printing or the print preview has been closed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onafterprint"><code>onafterprint</code></a></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    window.addEventListener('afterprint', (event) => {
      console.log('After print');
    });

Using the `onafterprint` event handler property:

    window.onafterprint = (event) => {
      console.log('After print');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#event-afterprint">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`afterprint_event`

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

-   Related events: [`beforeprint`](beforeprint_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/afterprint_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/afterprint_event</a>
