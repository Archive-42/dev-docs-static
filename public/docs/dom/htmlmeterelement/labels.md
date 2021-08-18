# HTMLMeterElement.labels

The `HTMLMeterElement.labels` read-only property returns a [`NodeList`](../nodelist) of the [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements associated with the [`<meter>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter) element.

## Syntax

    var labelElements = meter.labels;

### Return value

A [`NodeList`](../nodelist) containing the `<label>` elements associated with the `<meter>` element.

## Example

### HTML

    <label id="label1" for="test">Label 1</label>
    <meter id="test" min="0" max="100" value="70">70</meter>
    <label id="label2" for="test">Label 2</label>

### JavaScript

    window.addEventListener("DOMContentLoaded", function() {
      const meter = document.getElementById("test");
      for(var i = 0; i < meter.labels.length; i++) {
        console.log(meter.labels[i].textContent); // "Label 1" and "Label 2"
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-lfe-labels">HTML Living Standard<br />
<span class="small">The definition of 'labels' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-lfe-labels">HTML5<br />
<span class="small">The definition of 'labels' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`labels`

6

18

56

No

≤12.1

6

≤37

18

56

≤12.1

6

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement/labels" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMeterElement/labels</a>
