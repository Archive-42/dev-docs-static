MouseScrollEvent
================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MouseScrollEvent` interface represents events that occur due to the user moving a mouse wheel or similar input device.

**Do not use this interface for wheel events.**

Like [`MouseWheelEvent`](mousewheelevent), this interface is non-standard and deprecated. It was used in Gecko-based browsers only. Instead use the standard *[`WheelEvent`](wheelevent).*

Method overview
---------------

<table><tbody><tr class="odd"><td><code>void initMouseScrollEvent(in DOMString typeArg, in boolean canBubbleArg, in boolean cancelableArg, in nsIDOMAbstractView viewArg, in long detailArg, in long screenXArg, in long screenYArg, in long clientXArg, in long clientYArg, in boolean ctrlKeyArg, in boolean altKeyArg, in boolean shiftKeyArg, in boolean metaKeyArg, in unsigned short buttonArg, in nsIDOMEventTarget relatedTargetArg, in long axis);</code></td></tr></tbody></table>

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>axis</code> <span class="badge inline readonly">Read only </span></td><td><code>long</code></td><td>Indicates scroll direction.</td></tr></tbody></table>

Constants
---------

### Delta modes

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>HORIZONTAL_AXIS</code></td><td><code>0x01</code></td><td>The event is caused by horizontal wheel operation.</td></tr><tr class="even"><td><code>VERTICAL_AXIS</code></td><td><code>0x02</code></td><td>The event is caused by vertical wheel operation.</td></tr></tbody></table>

Methods
-------

`initMouseScrollEvent()`  
See [nsIDOMMouseScrollEvent::initMouseScrollEvent()](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIDOMMouseScrollEvent#initMouseScrollEvent%28%29).

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

`MouseScrollEvent`

No

No

3.5

No

No

No

No

No

4

No

No

No

See also
--------

-   `DOMMouseScroll`
-   `MozMousePixelScroll`
-   Non-gecko browsers' legacy mouse wheel event object: [`MouseWheelEvent`](mousewheelevent)
-   Standardized mouse wheel event object: [`WheelEvent`](wheelevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseScrollEvent</a>
