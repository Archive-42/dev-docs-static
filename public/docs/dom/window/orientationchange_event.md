Window: orientationchange event
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `orientationchange` event is fired when the orientation of the device has changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><span class="page-not-created"><code>onorientationchange</code></span></td></tr></tbody></table>

Example
-------

You can use the `orientationchange` event in an [`addEventListener`](../eventtarget/addeventlistener) method:

    window.addEventListener("orientationchange", function(event) {
      console.log("the orientation of the device is now " + event.target.screen.orientation.angle);
    });

Or use the <span class="page-not-created">`onorientationchange`</span> event handler property:

    window.onorientationchange = function(event) {
      console.log("the orientation of the device is now " + event.target.screen.orientation.angle);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://compat.spec.whatwg.org/#event-orientationchange">Compatibility Standard<br />
<span class="small">The definition of 'orientationchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`orientationchange_event`

No

No

No

No

No

No

Yes

Yes

44

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/orientationchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/orientationchange_event</a>
