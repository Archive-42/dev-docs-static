# InputEvent

The `InputEvent` interface represents an event notifying the user of editable content changes.

## Constructor

[`InputEvent()`](inputevent/inputevent)  
Creates an `InputEvent` object.

## Properties

_This interface inherits properties from its parents, [`UIEvent`](uievent) and [`Event`](event)._

[`InputEvent.data`](inputevent/data)<span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) with the inserted characters. This may be an empty string if the change doesn't insert text (such as when deleting characters, for example).

[`InputEvent.dataTransfer`](inputevent/datatransfer)<span class="badge inline readonly">Read only </span>  
Returns a [`DataTransfer`](datatransfer) object containing information about richtext or plaintext data being added to or removed from editable content.

[`InputEvent.inputType`](inputevent/inputtype)<span class="badge inline readonly">Read only </span>  
Returns the type of change for editable content such as, for example, inserting, deleting, or formatting text. See the property page for a complete list of input types.

[`InputEvent.isComposing`](inputevent/iscomposing)<span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the event is fired after `compositionstart` and before `compositionend`.

## Methods

_This interface inherits methods from its parents, [`UIEvent`](uievent) and [`Event`](event)._

[`InputEvent.getTargetRanges()`](inputevent/gettargetranges)  
Returns an array of static ranges that will be affected by a change to the DOM if the input event is not canceled.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/input-events/#interface-InputEvent">Input Events Level 2<br />
<span class="small">The definition of 'InputEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/#interface-inputevent">UI Events<br />
<span class="small">The definition of 'InputEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`data`

60

79

67

No

47

10.1

60

60

67

44

10.3

8.0

`dataTransfer`

60

79

67

No

47

10.1

60

60

67

44

10.3

8.0

`getTargetRanges`

60

79

87

75-87

No

47

10.1

60

60

87

79-87

44

10.3

8.0

`inputType`

60

79

66

No

47

10.1

60

60

66

44

10.3

8.0

`isComposing`

60

79

31

No

47

No

60

60

31

44

No

8.0

## See also

- [`beforeinput` event](htmlelement/beforeinput_event)
- [`input` event](htmlelement/input_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent</a>
