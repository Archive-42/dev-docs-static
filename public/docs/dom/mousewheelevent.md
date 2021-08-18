MouseWheelEvent
===============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MouseWheelEvent` interface represents events that occur due to the user turning a mouse wheel.

**Do not use this interface for wheel events.**

Like [`MouseScrollEvent`](mousescrollevent), this interface is non-standard and deprecated. It was used in non-Gecko browsers only. Instead use the standard *[`WheelEvent`](wheelevent).*

Properties
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>wheelDelta</code> <span class="badge inline readonly">Read only </span></td><td><code>long</code></td><td>The distance in pixels (defined as so by MSDN, but the actual usage is different, see <code>mousewheel</code>).</td></tr><tr class="even"><td><code>wheelDeltaX</code> <span class="badge inline readonly">Read only </span></td><td><code>long</code>?</td><td>The value along horizontal axis of <code>wheelDelta</code>.</td></tr><tr class="odd"><td><code>wheelDeltaY</code> <span class="badge inline readonly">Read only </span></td><td><code>long</code>?</td><td>The value along vertical axis of <code>wheelDelta</code>.</td></tr></tbody></table>

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

`MouseWheelEvent`

Yes

12

No

6

Yes

Yes

Yes

Yes

No

?

?

Yes

`wheelDelta`

No

12-79

No

9

No

No

No

No

No

No

No

No

`wheelDeltaX`

Yes

≤79

No

No

No

Yes

Yes

Yes

No

No

?

Yes

`wheelDeltaY`

Yes

≤79

No

No

No

Yes

Yes

Yes

No

No

?

Yes

See also
--------

-   An event type which is used by this event object: `mousewheel`
-   A standardized mouse wheel event object: [`WheelEvent`](wheelevent)
-   Gecko's legacy mouse wheel event object: [`MouseScrollEvent`](mousescrollevent)
-   The document in MSDN: [MouseWheelEvent object](https://msdn.microsoft.com/en-us/library/ie/ff974345%28v=vs.85%29.aspx)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseWheelEvent</a>
