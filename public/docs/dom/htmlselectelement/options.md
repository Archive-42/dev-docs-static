# HTMLSelectElement.options

The `HTMLSelectElement.options` read-only property returns a [`HTMLOptionsCollection`](../htmloptionscollection) of the [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements contained by the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element.

## Syntax

    var options = select.options;

### Return value

A [`HTMLOptionsCollection`](../htmloptionscollection) containing the `<option>` elements contained by the `<select>` element.

## Example

### HTML

    <label for="test">Label</label>
    <select id="test">
      <option value="1">Option 1</option>
      <option value="2">Option 2</option>
    </select>

### JavaScript

    window.addEventListener("DOMContentLoaded", function() {
      const select = document.getElementById("test");
      for(var i = 0; i < select.options.length; i++) {
        console.log(select.options[i].label); // "Option 1" and "Option 2"
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-options">HTML Living Standard<br />
<span class="small">The definition of 'options' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#htmlselectelement">HTML5<br />
<span class="small">The definition of 'options' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`options`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/options" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/options</a>
