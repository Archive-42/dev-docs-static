MediaStreamTrack.onoverconstrained
==================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MediaStreamTrack.onoverconstrained` event handler is a property called when the `overconstrained` event is received. Such an event is sent when the track is again able to send data.

Syntax
------

    track.onoverconstrained = function;

### Values

-   `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type <span class="page-not-created">`MediaStreamErrorEvent`</span>.

Example
-------

    dc.onoverconstrained = function() { alert("overconstrained event detected!"); };

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

`onoverconstrained`

Yes

12

Yes

No

Yes

11

Yes

Yes

?

?

11

Yes

See also
--------

-   The `overconstrained` event and its type, <span class="page-not-created">`MediaStreamErrorEvent`</span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onoverconstrained" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onoverconstrained</a>
