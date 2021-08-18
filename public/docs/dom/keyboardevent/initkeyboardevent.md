# KeyboardEvent.initKeyboardEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `KeyboardEvent.initKeyboardEvent()` method initializes the attributes of a keyboard event object. This method was introduced in draft of DOM Level 3 Events, but deprecated in newer draft. Gecko won't support this feature since implementing this method as experimental broke existing web apps (see [bug 999645](https://bugzilla.mozilla.org/show_bug.cgi?id=999645)). Web applications should use constructor instead of this if it's available.

## Syntax

    kbdEvent.initKeyboardEvent(typeArg, canBubbleArg, cancelableArg,
                               viewArg, charArg, keyArg,
                               locationArg, modifiersListArg, repeat)

### Parameters

_`typeArg`_  
The type of keyboard event; this will be one of `keydown`, `keypress`, or `keyup`.

_`canBubbleArg`_  
Whether or not the event can bubble.

_`cancelableArg`_  
Whether or not the event can be canceled.

_`viewArg`_  
The <span class="page-not-created">`WindowProxy`</span> it is associated to.

_`charArg`_  
The value of the char attribute.

_`keyArg`_  
The value of the key attribute.

_`locationArg`_  
The value of the location attribute.

_`modifiersListArg`_  
A whitespace-delineated list of modifier keys that should be considered to be active on the event's key. For example, specifying "Control Shift" indicates that the user was holding down the Control and Shift keys when pressing the key described by the event.

_`repeatArg`_  
The value of the repeat attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyboardEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/initKeyboardEvent</a>
