WindowEventHandlers.onbeforeprint
=================================

The `onbeforeprint` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `beforeprint` events for the current window. These events are raised before the print dialog window is opened.

The `beforeprint` and `afterprint` events allow pages to change their content before printing starts (perhaps to remove a banner, for example) and then revert those changes after printing has completed. In general, you should prefer the use of an `@media print` CSS at-rule, but it may be necessary to use these events in some cases.

Syntax
------

    window.addEventListener("beforeprint", function(event) { ... });
    window.onbeforeprint = function(event) { ... };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-window-onbeforeprint">HTML Living Standard<br />
<span class="small">The definition of 'onbeforeprint' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onbeforeprint`

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

-   [`Window.print()`](../window/print)
-   [`WindowEventHandlers.onafterprint`](onafterprint)
-   [Printing](https://developer.mozilla.org/en-US/docs/Web/Guide/Printing)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeprint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onbeforeprint</a>
