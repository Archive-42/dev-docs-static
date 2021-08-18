HTMLButtonElement.labels
========================

The `HTMLButtonElement.labels` read-only property returns a [`NodeList`](../nodelist) of the [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements associated with the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element.

Syntax
------

    var labelElements = button.labels;

### Return value

A [`NodeList`](../nodelist) containing the `<label>` elements associated with the `<button>` element.

Example
-------

### HTML

    <label id="label1" for="test">Label 1</label>
    <button id="test">Button</button>
    <label id="label2" for="test">Label 2</label>

### JavaScript

    window.addEventListener("DOMContentLoaded", function() {
      const button = document.getElementById("test");
      for(var i = 0; i < button.labels.length; i++) {
        console.log(button.labels[i].textContent); // "Label 1" and "Label 2"
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-lfe-labels">HTML Living Standard<br />
<span class="small">The definition of 'labels' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`labels`

6

18

56

No

≤12.1

5.1

≤37

18

56

≤12.1

5

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement/labels" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement/labels</a>
