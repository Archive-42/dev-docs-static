Event.initEvent()
=================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Event.initEvent()` method is used to initialize the value of an [`event`](../event) created using [`Document.createEvent()`](../document/createevent).

Events initialized in this way must have been created with the [`Document.createEvent()`](../document/createevent) method. This method must be called to set the event before it is dispatched, using [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent). Once dispatched, it doesn't do anything anymore.

**Do not use this method anymore as it is deprecated.**

Instead use specific event constructors, like [`Event()`](event). The page on [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) gives more information about the way to use these.

Syntax
------

    event.initEvent(type, bubbles, cancelable);

*`type`*  
Is a [`DOMString`](../domstring) defining the type of event.

*`bubbles`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) deciding whether the event should bubble up through the event chain or not. Once set, the read-only property [`Event.bubbles`](bubbles) will give its value.

*`cancelable`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) defining whether the event can be canceled. Once set, the read-only property [`Event.cancelable`](cancelable) will give its value.

Example
-------

    // Create the event.
    var event = document.createEvent('Event');

    // Create a click event that bubbles up and
    // cannot be canceled 
    event.initEvent('click', true, false);

    // Listen for the event.
    elem.addEventListener('click', function (e) {
      // e.target matches elem
    }, false);

    elem.dispatchEvent(event);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-initevent">DOM<br />
<span class="small">The definition of 'Event.initEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, deprecated it, superseded by event constructors.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-initEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.initEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initEvent`

Yes

12

17

Yes-17

Before Firefox 17, a call to this method after the dispatching of the event raised an exception instead of doing nothing.

Yes

Yes

Yes

Yes

Yes

17

Yes-17

Before Firefox 17, a call to this method after the dispatching of the event raised an exception instead of doing nothing.

Yes

Yes

Yes

See also
--------

-   The constructor to use instead of this deprecated method: [`Event()`](event). More specific constructors can be used too.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/initEvent</a>
