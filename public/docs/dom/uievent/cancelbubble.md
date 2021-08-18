UIEvent.cancelBubble
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `UIEvent.cancelBubble` property indicates if event bubbling for this event has been canceled or not. It is set to `false` by default, allowing the event to bubble up the DOM, if it is a bubbleable event. Setting this property to `true` stops the event from bubbling up the DOM. Not all events are allowed to bubble up the DOM.

Use [`Event.stopPropagation()`](../event/stoppropagation) instead of this non-standard method.

Syntax
------

    event.cancelBubble = bool;
    var bool = event.cancelBubble;

Specifications
--------------

*This property is not part of any specification.* Although the similar [`Event.cancelBubble`](../event/cancelbubble) property was included in [an old Working Draft of W3C DOM Level 2](https://www.w3.org/TR/1999/WD-DOM-Level-2-19990304/events.html#attribute-cancelBubble). Microsoft has a [description of it on MSDN](https://msdn.microsoft.com/en-us/library/ms533545(v=vs.85).aspx).

Browser compatibility
---------------------

No compatibility data found for `api.UIEvent.cancelBubble`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Event.cancelBubble`](../event/cancelbubble)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/cancelBubble" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/cancelBubble</a>
