# KeyboardEvent.isComposing

The `KeyboardEvent.isComposing` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the event is fired within a composition session, i.e. after [`compositionstart`](../element/compositionstart_event) and before [`compositionend`](../element/compositionend_event).

## Syntax

    var bool = event.isComposing;

## Example

    var kbdEvent = new KeyboardEvent("syntheticKey", false);
    console.log(kbdEvent.isComposing); // return false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-keyboardevent-iscomposing">UI Events<br />
<span class="small">The definition of 'KeyboardEvent.prototype.isComposing' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-isComposing">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.prototype.isComposing' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

56

≤79

31

No

43

10.1

56

56

31

43

10.3

6.0

## See also

- `compositionstart` and `compositionend`
- [`KeyboardEvent`](../keyboardevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/isComposing</a>
