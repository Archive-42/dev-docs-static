# CompositionEvent.initCompositionEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The ` initCompositionEvent``() ` method of the [`CompositionEvent`](../compositionevent) interface initializes the attributes of a `CompositionEvent` object instance.

## Syntax

     compositionEventInstance.initCompositionEvent(typeArg, canBubbleArg, cancelableArg, viewArg, dataArg, localeArg)

### Parameters

`typeArg`  
A [`DOMString`](../domstring) representing the type of composition event; this will be one of `compositionstart`, `compositionupdate`, or `compositionend`.

`canBubbleArg`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) specifying whether or not the event can bubble.

`cancelableArg`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) whether or not the event can be canceled.

`viewArg`  
The [`Window`](../window) object from which the event was generated.

`dataArg`  
A [`DOMString`](../domstring) representing the value of the `data` attribute.

`localeArg`  
A [`DOMString`](../domstring) representing the value of the `locale` attribute.

### Return value

Void.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#idl-interface-CompositionEvent-initializers">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'initCompositionEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initCompositionEvent`

Yes

12

9

Yes

No

Yes

Yes

Yes

9

?

Yes

Yes

## See also

- [`CompositionEvent`](../compositionevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent/initCompositionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent/initCompositionEvent</a>
