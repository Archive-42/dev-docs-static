# HTMLInputElement.setRangeText()

The `HTMLInputElement.setRangeText()` method replaces a range of text in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element with a new string.

## Syntax

    element.setRangeText(replacement);
    element.setRangeText(replacement, start, end [, selectMode]);

### Parameters

`replacement`  
The string to insert.

`start` <span class="badge inline optional">Optional</span>  
The 0-based index of the first character to replace. Defaults to the current `selectionStart` value (the start of the user's current selection).

`end` <span class="badge inline optional">Optional</span>  
The 0-based index of the character _after_ the last character to replace. Defaults to the current `selectionEnd` value (the end of the user's current selection).

`selectMode` <span class="badge inline optional">Optional</span>  
A string defining how the selection should be set after the text has been replaced. Possible values:

- `"select"` selects the newly inserted text.
- `"start"`moves the selection to just before the inserted text.
- `"end"` moves the selection to just after the inserted text.
- `"preserve"` attempts to preserve the selection. This is the default.

## Example

Click the button in this example to replace part of the text in the text box. The newly inserted text will be highlighted (selected) afterwards.

### HTML

    <input type="text" id="text-box" size="30" value="This text has NOT been updated.">
    <button onclick="selectText()">Update text</button>

### JavaScript

    function selectText() {
      const input = document.getElementById('text-box');
      input.focus();
      input.setRangeText('ALREADY', 14, 17, 'select');
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-textarea/input-setrangetext">HTML Living Standard<br />
<span class="small">The definition of 'HTMLInputElement.setSelectionRange()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-textarea/input-setrangetext">HTML5<br />
<span class="small">The definition of 'HTMLInputElement.setSelectionRange()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`setRangeText`

24

79

27

No

15

6.1

≤37

25

27

14

7

1.5

## See also

- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
- [`HTMLInputElement`](../htmlinputelement)
- [`Selection`](../selection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText</a>
