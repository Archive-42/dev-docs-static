# Document.getSelection()

The `getSelection()` property of the [`Document`](../document) interface returns a [`Selection`](../selection) object representing the range of text selected by the user, or the current position of the caret.

## Syntax

    getSelection()

### Parameters

None.

### Returns

A [`Selection`](../selection) object.

## Example

### Getting a Selection object

    let selection = document.getSelection();
    let selRange = selection.getRangeAt(0);
    // do stuff with the range

    console.log(selection); // Selection object

### String representation of the Selection object

Some functions (like [`Window.alert()`](../window/alert)) call [`toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString) automatically and the returned value is passed to the function. As a consequence, this will return the selected text and not the `Selection` object:

    alert(selection);

However, not all functions call `toString()` automatically. To use a `Selection` object as a string, call its `toString()` method directly:

    let selectedText = selection.toString();

## Related objects

You can call [`Window.getSelection()`](../window/getselection), which works identically to `Document.getSelection()`.

It is worth noting that currently `getSelection()` doesn't work on the content of [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements in Firefox. [`HTMLInputElement.setSelectionRange()`](../htmlinputelement/setselectionrange)) could be used to work around this.

Notice also the difference between _selection_ and _focus_. [`Document.activeElement`](activeelement) returns the focused element.

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#extensions-to-document-interface">Selection API<br />
<span class="small">The definition of 'Document.getSelection' in that specification.</span></a></td></tr></tbody></table>

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

`getSelection`

1

12

1

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getSelection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getSelection</a>
