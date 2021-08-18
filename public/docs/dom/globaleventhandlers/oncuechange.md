GlobalEventHandlers.oncuechange
===============================

The `oncuechange` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `cuechange` events.

The `cuechange` event fires when a [`TextTrack`](../texttrack) has changed the currently displaying cues. The event is sent to both the `TextTrack` and to the [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element the track is being presented by, if any; in the latter case, its handler is on an [`HTMLTrackElement`](../htmltrackelement) object.

Syntax
------

    element.oncuechange = handlerFunction;
    var handlerFunction = element.oncuechange;

`handlerFunction` is either `null` or a [JavaScript function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) specifying the handler for the event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-oncuechange">HTML Living Standard<br />
<span class="small">The definition of 'oncuechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oncuechange`

32

18

68

Added for the `<track>` element (`HTMLTrackElement`) in Firefox 68.

31

Added for the `TextTrack` interface in Firefox 31.

No

19

≤12.1-15

10.1

4.4.3

32

68

Added for the `<track>` element (`HTMLTrackElement`) in Firefox 68.

31

Added for the `TextTrack` interface in Firefox 31.

19

≤12.1-14

10.3

2.0

See also
--------

-   [Web Video Tracks Format (VTT)](../webvtt_api)
-   `cuechange`
-   [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track)
-   [DOM event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oncuechange</a>
