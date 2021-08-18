# InputEvent.isComposing

The `InputEvent.isComposing` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the event is fired after `compositionstart` and before `compositionend`.

## Syntax

    var bool = event.isComposing;

## Example

    var inputEvent = new InputEvent('syntheticInput', false);
    console.log(inputEvent.isComposing); // return false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-InputEvent-isComposing">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'InputEvent.isComposing' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

- `compositionstart` and `compositionend`
- [`InputEvent`](../inputevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/isComposing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/isComposing</a>
