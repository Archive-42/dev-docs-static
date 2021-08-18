KeyboardEvent.initKeyEvent()
============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `KeyboardEvent.initKeyEvent()` method is used to initialize the value of an event created using [`document.createEvent`](../document/createevent)`("KeyboardEvent")`. Events initialized in this way must have been created with the [`document.createEvent`](../document/createevent)`("KeyboardEvent")` method. `initKeyEvent()` must be called to set the event before it is [dispatched](../eventtarget/dispatchevent).

**Do not use this method anymore, use the [`KeyboardEvent()`](keyboardevent) constructor instead.**  
  
This method is based on early drafts of [Document Object Model (DOM) Level 2 Events Specification](https://www.w3.org/TR/DOM-Level-2-Events/events.html) and is implemented in Gecko-based browsers; other browsers implemented [`KeyboardEvent.initKeyboardEvent`](initkeyboardevent) based on early drafts of [Document Object Model (DOM) Level 3 Events Specification](https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/). Favor the modern constructor structure as the only cross-browser way of building events.

Syntax
------

    event.initKeyEvent (type, bubbles, cancelable, viewArg,
                        ctrlKeyArg, altKeyArg, shiftKeyArg, metaKeyArg,
                        keyCodeArg, charCodeArg)

### Parameters

*`type`*  
Is a [`DOMString`](../domstring) representing the type of event.

*`bubbles`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event should bubble up through the event chain or not (see [bubbles](../event/bubbles)).

*`cancelable`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) i indicating whether the event can be canceled (see [cancelable](../event/cancelable)).

*`viewArg`*  
Specifies the [`UIEvent.view`](../uievent/view); this value may be `null`.

*`ctrlKeyArg`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the virtual key to be generated is a combination of keys containing the Ctrl key.

*`altKeyArg`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the virtual key to be generated is a combination of keys containing the Alt key.

*`shiftKeyArg`*  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the virtual key to be generated is a combination of keys containing the Shift key.

*`metaKeyArg`*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the virtual key to be generated is a combination of keys containing the Meta key.

*`keyCodeArg`*  
Is a `unsigned long` representing the virtual key code value of the key which was depressed, otherwise `0`. See [`KeyboardEvent.keyCode`](keycode) for the list of key codes.

*`charCodeArg`*  
Is a `unsigned long` representingthe Unicode character associated with the depressed key otherwise `0`.

Example
-------

    var event = document.createEvent('KeyboardEvent'); // create a key event
    // define the event
    event.initKeyEvent("keypress",       // typeArg,
                       true,             // canBubbleArg,
                       true,             // cancelableArg,
                       null,             // viewArg,  Specifies UIEvent.view. This value may be null.
                       false,            // ctrlKeyArg,
                       false,            // altKeyArg,
                       false,            // shiftKeyArg,
                       false,            // metaKeyArg,
                        9,               // keyCodeArg,
                        0);              // charCodeArg);

    document.getElementById('blah').dispatchEvent(event);

Specifications
--------------

This implementation of keyboard events is based on the key events spec in the [early versions of DOM 2 Events](https://www.w3.org/TR/1999/WD-DOM-Level-2-19990923/events.html), later removed from that spec.

The `initKeyEvent` is the current Gecko equivalent of the DOM Level 3 Events (initially drafted and also deprecated in favor of [`KeyboardEvent()`](keyboardevent) <span class="page-not-created">`Keyboard.initKeyboardEvent()`</span> method with the following arguments :

    typeArg of type DOMString
    canBubbleArg of type boolean
    cancelableArg of type boolean
    viewArg of type views::AbstractView
    keyIdentifierArg of type DOMString
    keyLocationArg of type unsigned long
    modifiersList of type DOMString);

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyEvent</a>
