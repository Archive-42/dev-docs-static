# RadioNodeList.value

If the underlying element collection contains radio buttons, the `RadioNodeList.value` property represents the checked radio button. On retrieving the `value` property, the `value` of the currently `checked` radio button is returned as a string. If the collection does not contain any radio buttons or none of the radio buttons in the collection is in `checked` state, the empty string is returned. On setting the `value` property, the first radio button input element whose `value` property is equal to the new value will be set to `checked`.

## Syntax

    value = radioNodeList.value;
    radioNodeList.value = string;

## Example

### HTML

    <form>
      <label><input type="radio" name="color" value="blue">Blue</label>
      <label><input type="radio" name="color" value="red">Red</label>
    </form>

### JavaScript

    // Get the form
    const form = document.forms[0];

    // Get the form's radio buttons
    const radios = form.elements['color'];

    // Choose the "red" option
    radios.value = 'red';

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-radionodelist-value">HTML Living Standard<br />
<span class="small">The definition of 'RadioNodeList.value' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`value`

34

18

33

Yes

Yes

10

≤37

Yes

33

Yes

9

Yes

## See also

- The [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form), [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset), [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList/value</a>
