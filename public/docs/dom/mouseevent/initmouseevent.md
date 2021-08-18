# MouseEvent.initMouseEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MouseEvent.initMouseEvent()` method initializes the value of a mouse event once it's been created (normally using the [`Document.createEvent()`](../document/createevent) method).

Events initialized in this way must have been created with the [`Document.createEvent()`](../document/createevent) method. This method must be called to set the event before it is dispatched, using [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent). Once dispatched, it doesn't do anything anymore.

**Note**

**Do not use this method anymore as it is deprecated.**

Instead use specific event constructors, like [`MouseEvent()`](mouseevent). The page on [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events) gives more information about the way to use these.

## Syntax

    event.initMouseEvent(type, canBubble, cancelable, view,
                         detail, screenX, screenY, clientX, clientY,
                         ctrlKey, altKey, shiftKey, metaKey,
                         button, relatedTarget);

### Parameters

`type`  
the string to set the event's [`type`](../event/type) to. Possible types for mouse events include: `click`, `mousedown`, `mouseup`, `mouseover`, `mousemove`, `mouseout`.

`canBubble`  
whether or not the event can bubble. Sets the value of [`Event.bubbles`](../event/bubbles).

`cancelable`  
whether or not the event's default action can be prevented. Sets the value of [`Event.cancelable`](../event/cancelable).

`view`  
the event's AbstractView. You should pass the [`window`](../window) object here. Sets the value of [`UIEvent.view`](../uievent/view).

`detail`  
the event's mouse click count. Sets the value of [`UIEvent.detail`](../uievent/detail).

`screenX`  
the event's screen x coordinate. Sets the value of [`MouseEvent.screenX`](screenx).

`screenY`  
the event's screen y coordinate. Sets the value of [`MouseEvent.screenY`](screeny).

`clientX`  
the event's client x coordinate. Sets the value of [`MouseEvent.clientX`](clientx).

`clientY`  
the event's client y coordinate. Sets the value of [`MouseEvent.clientY`](clienty).

`ctrlKey`  
whether or not control key was depressed during the Event. Sets the value of [`MouseEvent.ctrlKey`](ctrlkey).

`altKey`  
whether or not alt key was depressed during the Event. Sets the value of [`MouseEvent.altKey`](altkey).

`shiftKey`  
whether or not shift key was depressed during the Event. Sets the value of [`MouseEvent.shiftKey`](shiftkey).

`metaKey`  
whether or not meta key was depressed during the Event. Sets the value of [`MouseEvent.metaKey`](metakey).

`button`  
the event's mouse [`button`](button).

`relatedTarget`  
the event's [related EventTarget](relatedtarget). Only used with some event types (e.g., `mouseover` and `mouseout`). In other cases, pass `null`.

## Example

### HTML

    <div style="background:red; width:180px; padding:10px;">
      <div id="out"></div>
      <input type="text">
    </div>

### JavaScript

    document.body.onclick = function(){
      e = arguments[0];
      var dt = e.target,stag = dt.tagName.toLowerCase();
      document.getElementById("out").innerHTML = stag;
    };

    var simulateClick = function(){
      var evt = document.createEvent("MouseEvents");
      evt.initMouseEvent("click", true, true, window, 0, 0, 0, 80, 20, false, false, false, false, 0, null);
      document.body.dispatchEvent(evt);
    }

    simulateClick();

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#idl-interface-MouseEvent-initializers">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.initMouseEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, deprecated.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-initMouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.initMouseEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initMouseEvent`

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

## See also

- [`MouseEvent()`](mouseevent) constructor, the modern standard way of creating a [`MouseEvent`](../mouseevent)
- [`Event.initEvent()`](../event/initevent) is a simpler method serving a similar purpose. It is also obsolete and shouldn't be used any more.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/initMouseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/initMouseEvent</a>
