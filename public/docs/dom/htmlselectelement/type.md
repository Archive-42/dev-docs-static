# HTMLSelectElement.type

The `HTMLSelectElement.type` read-only property returns the form control's `type`.

## Syntax

    var str = selectElt.type;

The possible values are:

- `"select-multiple"` if multiple values can be selected.
- `"select-one"` if only one value can be selected.

## Example

    switch (select.type) {
      case 'select-multiple':
        // Multiple values may be selected
        break;
      case 'select-one':
        // Only one value may be selected
        break;
      default:
        // Non-standard value (or this isn't a SELECT element)
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-type">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>, the latest snapshot.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-type">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Is a snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. No change from {{SpecName("DOM2 HTML")}}.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-58783172">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-58783172">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

1

12

1

1

2

3

1

18

4

10.1

1

1.0

## See also

- The [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) HTML element, implementing this interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/type</a>
