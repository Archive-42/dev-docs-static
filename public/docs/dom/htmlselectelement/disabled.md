# HTMLSelectElement.disabled

The `HTMLSelectElement.disabled` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the `disabled` HTML attribute, which indicates whether the control is disabled. If it is disabled, it does not accept clicks. A disabled element is unusable and un-clickable.

## Syntax

    aSelectElement.disabled = aBool;

## Example

### HTML

    <label>
      Allow drinks?
      <input id="allow-drinks" type="checkbox"/>
    </label>

    <label for="drink-select">Drink selection:</label>
    <select id="drink-select" disabled>
      <option value="1">Water</option>
      <option value="2">Beer</option>
      <option value="3">Pepsi</option>
      <option value="4">Whisky</option>
    </select>

### JavaScript

    var allowDrinksCheckbox = document.getElementById("allow-drinks");
    var drinkSelect = document.getElementById("drink-select");

    allowDrinksCheckbox.addEventListener("change", function(event) {
      if (event.target.checked) {
        drinkSelect.disabled = false;
      } else {
        drinkSelect.disabled = true;
      }
    }, false);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-fe-disabled">HTML Living Standard<br />
<span class="small">The definition of 'disabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#dom-select-disabled">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.</td></tr></tbody></table>

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

`disabled`

1

12

1

5.5

9

3

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/disabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement/disabled</a>
