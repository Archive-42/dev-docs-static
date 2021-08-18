# InputEvent.inputType

The `inputType` read-only property of the [`InputEvent`](../inputevent) interface returns the type of change made to editable content. Possible changes include for example inserting, deleting, and formatting text.

## Syntax

    var aString = inputEvent.inputType;

### Value

A [`DOMString`](../domstring) containing the type of input that was made. There are many possible values, such as `insertText`, `deleteContentBackward`, `insertFromPaste`, and `formatBold`. For a complete list of the available input types, see the [Attributes section of the Input Events Level 1 spec](https://rawgit.com/w3c/input-events/v1/index.html#interface-InputEvent-Attributes).

## Examples

This example logs the `inputType` for [input events](../htmlelement/input_event) on an editable [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div).

### HTML

    <p id="log">Input type: </p>
    <div contenteditable="true" style="margin: 20px;padding: 20px;border:2px dashed red;">
      <p>Some sample text. Try inserting line breaks, or deleting text in different ways, or pasting different content in.</p>
      <hr>
      <ul>
        <li>A sample</li>
        <li>bulleted</li>
        <li>list.</li>
      </ul>
      <p>Another paragraph.</p>
    </div>

### JavaScript

    const log = document.getElementById('log');
    const editable = document.querySelector('div[contenteditable]');
    editable.addEventListener('input', logInputType);

    function logInputType(event) {
      log.textContent = `Input type: ${event.inputType}`;
    }

### Result

Try editing the text inside the `<div>` and see what happens.

**Note**: See also [Masayuki Nakano's InputEvent test suite](https://d-toybox.com/studio/lib/input_event_viewer.html) for a more detailed example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-inputevent-inputtype">UI Events<br />
<span class="small">The definition of 'inputType' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`insertFromPasteAsQuotation`

No

No

67

No

No

?

No

No

67

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/inputType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/inputType</a>
