# InputEvent.data

The `data` read-only property of the [`InputEvent`](../inputevent) interface returns a [`DOMString`](../domstring) with inserted characters. This may be an empty string if the change doesn't insert text, such as when characters are deleted.

## Syntax

    var aString = inputEvent.data;

### Value

A [`DOMString`](../domstring).

## Examples

In the following example, an event listener receives the [input](../htmlelement/input_event) event. Any textual change to the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element is retrieved by `InputEvent.data` and inserted into a paragraph using the `Node.textContent` property.

    <p>Some text to copy and paste.</p>

    <input type="text">

    <p class="result"></p>

    var editable = document.querySelector('input');
    var result = document.querySelector('.result');

    editable.addEventListener('input', (e) => {
      result.textContent = "Inputted text: " + e.data;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/input-events/#dfn-data">Input Events Level 2<br />
<span class="small">The definition of 'data' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/data</a>
