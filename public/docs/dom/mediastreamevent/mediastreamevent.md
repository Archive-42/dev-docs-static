MediaStreamEvent()
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MediaStreamEvent()` constructor creates a new [`MediaStreamEvent`](../mediastreamevent).

Syntax
------

     var event = new MediaStreamEvent(type, mediaStreamEventInit);

### Values

*type*  
Is a [`DOMString`](../domstring) containing the name of the event, like `addstream` or `removestream`.

*mediaStreamEventInit*  
Is a `MediaStreamEventInit` dictionary, having the following fields:

-   `"stream"` of type [`MediaStream`](../mediastream) representing the stream being concerned by the event.
-   `"bubbles"`, optional and defaulting to `false`, inherited from `EventInit`, and indicating if the event must bubble or not.
-   `"cancelable"`, optional and defaulting to `false`, inherited from `EventInit`, and indicating if the event can be canceled or not.

Example
-------

    // s is a MediaStream
    var event = new MediaStreamEvent("addstream", {"stream": s});

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

`MediaStreamEvent`

Yes

15

Yes

No

Yes

?

Yes

Yes

?

Yes

?

Yes

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent/MediaStreamEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent/MediaStreamEvent</a>
