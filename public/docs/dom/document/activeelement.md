# Document.activeElement

The `activeElement` read-only property of the [`Document`](../document) interface returns the [`Element`](../element) within the DOM that currently has focus.

Often `activeElement` will return a [`HTMLInputElement`](../htmlinputelement) or [`HTMLTextAreaElement`](../htmltextareaelement) object if it has the text selection at the time. If so, you can get more detail by using the object's <span class="page-not-created">`selectionStart`</span> and <span class="page-not-created">`selectionEnd`</span> properties. Other times the focused element might be a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element (menu) or an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, of `type` `"button"`, `"checkbox"`, or `"radio"`.

Typically a user can press the tab key to move the focus around the page among focusable elements, and use the space bar to activate one (that is, to press a button or toggle a radio button). Which elements are focusable varies depending on the platform and the browser's current configuration. For example, on macOS systems, elements that aren't text input elements are not typically focusable by default.

**Note:** Focus (which element is receiving user input events) is not the same thing as selection (the currently highlighted part of the document). You can get the current selection using [`window.getSelection()`](../window/getselection).

## Syntax

    element = document.activeElement

### Value

The [`Element`](../element) which currently has focus, [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) or `null` if there is no focused element.

## Example

### HTML

    <p>Select some text from one of the text areas below:</p>

    <form>
      <textarea name="ta-example-one" id="ta-example-one" rows="7" cols="40">This is Text Area One. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tincidunt, lorem a porttitor molestie, odio nibh iaculis libero, et accumsan nunc orci eu dui.</textarea>
      <textarea name="ta-example-two" id="ta-example-two" rows="7" cols="40">This is Text Area Two. Fusce ullamcorper, nisl ac porttitor adipiscing, urna orci egestas libero, ut accumsan orci lacus laoreet diam. Morbi sed euismod diam.</textarea>
    </form>

    <p>Active element ID: <b id="output-element"></b></p>
    <p>Selected text: <b id="output-text"></b></p>

### JavaScript

    function onMouseUp(e) {
      const activeTextarea = document.activeElement;
      const selection = activeTextarea.value.substring(
        activeTextarea.selectionStart, activeTextarea.selectionEnd
      );

      const outputElement = document.getElementById('output-element');
      const outputText = document.getElementById('output-text');
      outputElement.innerHTML = activeTextarea.id;
      outputText.innerHTML = selection;
    }

    const textarea1 = document.getElementById('ta-example-one');
    const textarea2 = document.getElementById('ta-example-two');
    textarea1.addEventListener('mouseup', onMouseUp, false);
    textarea2.addEventListener('mouseup', onMouseUp, false);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-document-activeelement">HTML Living Standard<br />
<span class="small">The definition of 'activeElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`activeElement`

1

12

3

6

≤12.1

4

1

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement</a>
