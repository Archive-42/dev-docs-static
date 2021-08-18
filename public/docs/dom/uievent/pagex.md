UIEvent.pageX
=============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The non-standard, read-only [`UIEvent`](../uievent) property `pageX` returns the horizontal coordinate of the event relative to the whole document.

This property was never part of any standard, and was only implemented across a subset of browsers, and only for a limited number of versions. A standardized version of [`pageX`](../mouseevent/pagex) was added to the [`MouseEvent`](../mouseevent) interface, however, and is well-supported. You should not expect to find `pageX` on any non-mouse events. Do not look for `pageX` on any non-mouse events in new code and update existing code as soon as possible.

Syntax
------

    var pos = event.pageX

### Value

An integer value, in pixels, indicating the X coordinate at which the mouse pointer was located when the event occurred. This value is relative to the left edge of the entire document, regardless of the current horizontal scrolling offset of the document.

Examples
--------

For an example, see the documentation for the standard [`MouseEvent.pageX`](../mouseevent/pagex) property, which you should use instead.

Specifications
--------------

*This property is not part of any specification. See [`MouseEvent.pageX`](../mouseevent/pagex) instead.*

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

`pageX`

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

12

?

9

?

Yes

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

Yes-44

Replaced by `MouseEvent.pageX` in version 45.

?

?

Yes

Yes-4.0

Replaced by `MouseEvent.pageX` in Samsung Internet 5.0.

See also
--------

-   The standard [`MouseEvent.pageX`](../mouseevent/pagex) property
-   [`MouseEvent.pageY`](../mouseevent/pagey) (replacement for `UIEvent.pageY`)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/pageX</a>
