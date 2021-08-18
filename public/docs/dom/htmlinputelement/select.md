HTMLInputElement.select()
=========================

The `HTMLInputElement.select()` method selects all the text in a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element or in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element that includes a text field.

Syntax
------

    element.select();

Example
-------

Click the button in this example to select all the text in the `<input>` element.

### HTML

    <input type="text" id="text-box" size="20" value="Hello world!">
    <button onclick="selectText()">Select text</button>

### JavaScript

    function selectText() {
      const input = document.getElementById('text-box');
      input.focus();
      input.select();
    }

### Result

Notes
-----

Calling `element.select()` will not necessarily focus the input, so it is often used with [`HTMLOrForeignElement.focus`](../htmlorforeignelement/focus).

In browsers where it is not supported, it is possible to replace it with a call to [HTMLInputElement.setSelectionRange()](setselectionrange) with parameters 0 and the input's value length:

    <input onClick="this.select();" value="Sample Text" />
    <!-- equivalent to -->
    <input onClick="this.setSelectionRange(0, this.value.length);" value="Sample Text" />

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-textarea/input-select">HTML Living Standard<br />
<span class="small">The definition of 'select' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`select`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

See also
--------

-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
-   [`HTMLInputElement`](../htmlinputelement)
-   [`HTMLInputElement.setSelectionRange`](setselectionrange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select</a>
