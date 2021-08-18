# HTMLSelectElement.item()

The `HTMLSelectElement.item()` method returns the [`Element`](../element) corresponding to the [`HTMLOptionElement`](../htmloptionelement) whose position in the options list corresponds to the index given in the parameter, or `null` if there are none.

In JavaScript, using the array bracket syntax with an `unsigned long`, like `selectElt[index]` is equivalent to ` selectElt``.namedItem(index) `.

## Syntax

    var item = collection.item(index);
    var item = collection[index];

### Parameters

- `index` is an `unsigned long`.

### Return value

- `item` is a [`HTMLOptionElement`](../htmloptionelement).

## Examples

### HTML

    <form>
      <select id="myFormControl">
        <option id="o1">Opt 1</option>
        <option id="o2">Opt 2</option>
      </select>
    </form>

### JavaScript

    // Returns the HTMLOptionElement representing #o2
    elem1 = document.forms[0]['myFormControl'][1];

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-select-item">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement.item()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-item">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement.item()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a></td></tr></tbody></table>

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

`item`

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

## See also

- [`HTMLSelectElement`](../htmlselectelement) that implements it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/item</a>
