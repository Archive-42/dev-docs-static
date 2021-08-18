# InputEvent()

The `InputEvent()` constructor creates a new [`InputEvent`](../inputevent).

## Syntax

     event = new InputEvent(typeArg, inputEventInit);

### Values

_typeArg_  
Is a [`DOMString`](../domstring) representing the name of the event.

_inputEventInit_<span class="badge inline optional">Optional</span>  
Is a `InputEventInit` dictionary, having the following fields:

- `inputType`: (Optional) A string specifying the type of change for editable content such as, for example, inserting, deleting, or formatting text.
- `data`: (Optional) A string containing characters to insert. This may be an empty string if the change doesn't insert text (such as when deleting characters, for example).
- `dataTransfer`: (Optional) A [`DataTransfer`](../datatransfer) object containing information about richtext or plaintext data being added to or removed from editable content.
- `isComposing`: (Optional) A boolean indicating that the event is part of a composition session, meaning it is after a `compositionstart` event but before a `compositionend` event. The default is `false`.
- `ranges`: (Optional) An array of static ranges that will be affected by a change to the DOM if the input event is not canceled.

_The `InputEventInit` dictionary also accepts fields from [`UIEventInit`](../uievent/uievent) and from [`EventInit`](../event/event) dictionaries._

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

`InputEvent`

60

79

31

No

47

10.1

60

60

31

44

10.3

8.0

## See also

- [`InputEvent`](../inputevent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/InputEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/InputEvent</a>
