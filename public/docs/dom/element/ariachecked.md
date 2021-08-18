# Element.ariaChecked

### Note

The `ariaChecked` property of the [`Element`](../element) interface reflects the value of the `aria-checked` attribute, which indicates the current "checked" state of checkboxes, radio buttons, and other widgets that have a checked state.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="checkbox"` as this element has built in semantics and does not require ARIA attributes.

## Syntax

    var ariaChecked = element.ariaChecked;
    element.ariaChecked = ariaChecked

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The element is checked.

`"mixed"`  
Indicates a mixed mode value for a tri-state checkbox or menuitemcheckbox.

`"false"`  
The element supports being checked but is not currently checked.

`"undefined"`  
The element does not support being checked.

## Examples

In this example the `aria-checked` attribute on the element with an ID of `checkBoxInput` is set to "false" indicating that this input is currently unchecked. Using `ariaChecked` we update the value to "true".

    <span role="checkbox" id="checkBoxInput" aria-checked="false" tabindex="0" aria-labelledby="chk1-label">
    </span> <label id="chk1-label">Remember my preferences</label>

    let el = document.getElementById('checkBoxInput');
    console.log(el.ariaChecked); // "false"
    el.ariaChecked = "true"
    console.log(el.ariaChecked); // "true"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariachecked">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaChecked' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaChecked`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

## See also

- [ARIA: checkbox role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/checkbox_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaChecked" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaChecked</a>
