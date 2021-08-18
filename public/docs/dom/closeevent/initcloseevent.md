# CloseEvent.initCloseEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `CloseEvent.initCloseEvent()` method initializes the value of a close event once it's been created (normally using the [`Document.createEvent()`](../document/createevent) method).

Events initialized in this way must have been created with the [`Document.createEvent()`](../document/createevent) method. This method must be called to set the event before it is dispatched, using [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent). Once dispatched, it doesn't do anything anymore.

**Do not use this method anymore as it is deprecated.**

Instead use specific event constructors, like <span class="page-not-created">`CloseEvent()`</span>. The page on [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) gives more information about the way to use these.

## Syntax

    event.initMouseEvent(type, canBubble, cancelable, wasClean, reasonCode, reason);

### Parameters

_`type`_  
the string to set the event's [`type`](../event/type) to. Possible types for mouse events include: `click`, `mousedown`, `mouseup`, `mouseover`, `mousemove`, `mouseout`.

_`canBubble`_  
whether or not the event can bubble. Sets the value of [`Event.bubbles`](../event/bubbles).

_`cancelable`_  
whether or not the event's default action can be prevented. Sets the value of [`Event.cancelable`](../event/cancelable).

_`wasClean`_  
whether or not the connection was cleanly closed.

`reasonCode`  
the reason of the close.

`reason`  
a [`DOMString`](../domstring) describing the reason of the close in shuman-readable way.

## Specifications

_This is no part of any specifications, though it was in some early drafts._

## Browser compatibility

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

`initCloseEvent`

No

12-79

8-41

No

No

No

No

No

8-41

No

No

No

## See also

- [`CloseEvent()`](closeevent) constructor, the modern standard way of creating a [`CloseEvent`](../closeevent)
- [`Event.initEvent()`](../event/initevent) is a simpler method serving a similar purpose. It is also obsolete and shouldn't be used any more.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent/initCloseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent/initCloseEvent</a>
