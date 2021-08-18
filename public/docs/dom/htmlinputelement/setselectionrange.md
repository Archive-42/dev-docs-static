HTMLInputElement.setSelectionRange()
====================================

The `HTMLInputElement.setSelectionRange()` method sets the start and end positions of the current text selection in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element.

Optionally, in newer browser versions, you can specify the direction in which selection should be considered to have occurred. This lets you indicate, for example, that the selection was set by the user clicking and dragging from the end of the selected text toward the beginning.

This method updates the `HTMLInputElement.selectionStart`, `selectionEnd`, and `selectionDirection` properties in one call.

Note that accordingly to the [WHATWG forms spec](https://html.spec.whatwg.org/multipage/forms.html#concept-input-apply) `selectionStart`, `selectionEnd` properties and `setSelectionRange` method apply only to inputs of types text, search, URL, tel and password. Chrome, starting from version 33, throws an exception while accessing those properties and method on the rest of input types. For example, on input of type number: "Failed to read the 'selectionStart' property from 'HTMLInputElement': The input element's type ('number') does not support selection".

If you wish to select **all** text of an input element, you can use the [HTMLInputElement.select()](select) method instead.

Syntax
------

    element.setSelectionRange(selectionStart, selectionEnd [, selectionDirection]);

### Parameters

If `selectionEnd` is less than `selectionStart`, then both are treated as the value of `selectionEnd`.

`selectionStart`  
The 0-based index of the first selected character. An index greater than the length of the element's value is treated as pointing to the end of the value.

`selectionEnd`  
The 0-based index of the character *after* the last selected character. An index greater than the length of the element's value is treated as pointing to the end of the value.

 `selectionDirection` <span class="badge inline optional">Optional</span>   
A string indicating the direction in which the selection is considered to have been performed. Possible values:

-   `"forward"`
-   `"backward"`
-   `"none"` if the direction is unknown or irrelevant. Default value.

Example
-------

Click the button in this example to select the third, fourth, and fifth characters in the text box ("zil" in the word "Mozilla").

### HTML

    <input type="text" id="text-box" size="20" value="Mozilla">
    <button onclick="selectText()">Select text</button>

### JavaScript

    function selectText() {
      const input = document.getElementById('text-box');
      input.focus();
      input.setSelectionRange(2, 5);
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-textarea/input-setselectionrange">HTML Living Standard<br />
<span class="small">The definition of 'HTMLInputElement.setSelectionRange()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#dom-textarea/input-setselectionrange">HTML 5.1<br />
<span class="small">The definition of 'HTMLInputElement.setSelectionRange()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-textarea/input-setselectionrange">HTML5<br />
<span class="small">The definition of 'HTMLInputElement.setSelectionRange()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`setSelectionRange`

1

12

1

9

8

3

1

18

4

10.1

1

1.0

See also
--------

-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
-   [`HTMLInputElement`](../htmlinputelement)
-   [`Selection`](../selection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange</a>
