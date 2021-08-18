# InputEvent.dataTransfer

The `dataTransfer` read-only property of the [`InputEvent`](../inputevent) interface returns a [`DataTransfer`](../datatransfer) object containing information about richtext or plaintext data being added to or removed from editable content.

## Syntax

    var dataTransfer = inputEvent.dataTransfer

### Value

A [`DataTransfer`](../datatransfer) object.

## Examples

In the following simple example we've set up an event listener on the [input](../htmlelement/input_event) event so that when any content is pasted into the contenteditable [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element, its HTML source is retrieved via the `InputEvent.dataTransfer.getData()` method and reported in the paragraph below the input.

Try copying and pasting some of the content provided to see the effects.

    <p><span style="font-weight: bold; color: blue">Whoa, bold blue text!</span></p>
    <p><span style="font-style: italic; color: red">Exciting: italic red text!</span></p>
    <p>Boring normal text ;-(</p>

    <hr>

    <p contenteditable="true">Go on, try pasting some content into this editable paragraph and see what happens!</p>

    <p class="result"></p>

    var editable = document.querySelector('p[contenteditable]');
    var result = document.querySelector('.result')
    var dataTransferObj;

    editable.addEventListener('input', (e) => {
      result.textContent = e.dataTransfer.getData('text/html');
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/input-events/#dom-inputevent-datatransfer">Input Events Level 2<br />
<span class="small">The definition of 'dataTransfer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/dataTransfer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputEvent/dataTransfer</a>
