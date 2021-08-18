UIEvent.initUIEvent()
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `UIEvent.initUIEvent()` method initializes a UI event once it's been created.

Events initialized in this way must have been created with the [`Document.createEvent()`](../document/createevent) method. This method must be called to set the event before it is dispatched, using [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent). Once dispatched, it doesn't do anything anymore.

**Do not use this method anymore as it is deprecated.**

Instead use specific event constructors, like [`UIEvent()`](uievent). The page on [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) gives more information about the way to use these.

Syntax
------

    event.initUIEvent(type, canBubble, cancelable, view, detail)

### Parameters

*`type`*  
Is a [`DOMString`](../domstring) defining the type of event.

*`canBubble`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) deciding whether the event should bubble up through the event chain or not. Once set, the read-only property [`Event.bubbles`](../event/bubbles) will give its value.

*`cancelable`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) defining whether the event can be canceled. Once set, the read-only property [`Event.cancelable`](../event/cancelable) will give its value.

*`view`*  
Is the <span class="page-not-created">`WindowProxy`</span> associated with the event.

*`detail`*  
Is an `unsigned long` specifying some detail information about the event, depending on the type of event. For mouse events, it indicates how many times the mouse has been clicked on a given screen location.

Example
-------

    var e = document.createEvent("UIEvent");
    // creates a click event that bubbles, can be cancelled,
    // and with its view and detail property initialized to window and 1,
    // respectively
    e.initUIEvent("click", true, true, window, 1);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-UIEvent-initUIEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent.initUIEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, deprecated.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-UIEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'UIEvent.initUIEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initUIEvent`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`UIEvent`](../uievent)
-   The constructor to use instead of this deprecated method: [`UIEvent()`](uievent). More specific constructors can be used too.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/initUIEvent</a>
