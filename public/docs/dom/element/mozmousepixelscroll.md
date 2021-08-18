Element: MozMousePixelScroll event
==================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The Firefox-only, *non-standard*, and *obsolete* `MozMousePixelScroll` event is fired at an [`Element`](../element) asynchronously when a mouse wheel or similar device is operated. It's represented by the [`MouseScrollEvent`](../mousescrollevent) interface.

**Important:** Do not use this non-standard and obsolete event. Instead, you should always use the standard [`wheel`](wheel_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mousescrollevent"><code>MouseScrollEvent</code></a> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td></tr></tbody></table>

Getting the distance scrolled
-----------------------------

The event's [`detail`](../uievent/detail) property indicates the scroll distance in terms of lines, with negative values indicating the scrolling movement is either toward the bottom or toward the right, and positive values indicating scrolling to the top or left.

If the platform's native mouse wheel events indicate the scroll distance in terms of lines or pages, the value of `detail` is computed using that value and the line height or page width/height of the nearest ancestor scrollable element that contains the target element.

**Note:** On macOS, the scroll distance (and therefore the value of `detail`) is computed based on the accelerated scroll distance.

The value of `detail` is never 0 if the events are legitimate.

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

`MozMousePixelScroll`

No

≤18-79

Yes

No

No

No

No

No

Yes

No

No

No

See also
--------

-   [`MouseScrollEvent`](../mousescrollevent)
-   Gecko's legacy line or page scroll event: `DOMMouseScroll`
-   Non-Gecko browsers' legacy mouse wheel event: `mousewheel`
-   Standardized wheel event: `wheel`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/MozMousePixelScroll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/MozMousePixelScroll</a>
