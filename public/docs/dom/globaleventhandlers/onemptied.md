GlobalEventHandlers.onemptied
=============================

The `onemptied` property sets and returns the [event handler](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the `emptied` event.

Syntax
------

    element.onemptied = handlerFunction;
    var handlerFunction = element.onemptied;

`handlerFunction` should be either `null` or a [JavaScript function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) specifying the handler for the event.

Notes
-----

See the [DOM event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) page for information on working with `on...` handlers.

The `emptied` event is fired when the media has become empty; for example, this event is sent if the media has already been loaded (or partially loaded), and the `load()` method is called to reload it.

See the `emptied` event documentation for more information about the event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-onemptied">HTML Living Standard<br />
<span class="small">The definition of 'onemptied' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onemptied`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onemptied" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onemptied</a>
