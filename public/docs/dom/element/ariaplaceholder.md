# Element.ariaPlaceholder

### Note

The `ariaPlaceholder` property of the [`Element`](../element) interface reflects the value of the `aria-placeholder` attribute, which defines a short hint intended to aid the user with data entry when the control has no value.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="text"` or a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) as these have built in semantics and do not require ARIA attributes.

## Syntax

    var ariaPlaceholder = element.ariaPlaceholder;
    element.ariaPlaceholder = ariaPlaceholder

### Value

A [`DOMString`](../domstring).

## Examples

In this example the `aria-placeholder` attribute on the element with an ID of `txtBoxInput` has been set to a string. Using `ariaPlaceholder` we update the string to another value.

    <div id="txtboxLabel">Enter your five-digit zipcode</div>
    <div role="textbox" id="txtBoxInput" contenteditable="true" aria-placeholder="5-digit zipcode" aria-labelledby="txtboxLabel"></div>

    let el = document.getElementById('txtBoxInput');
    console.log(el.ariaPlaceholder); // "5-digit zipcode"
    el.ariaPlaceholder = "12345"
    console.log(el.ariaPlaceholder); // "12345"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaplaceholder">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaPlaceholder' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaPlaceholder`

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

- [ARIA: textbox role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/textbox_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPlaceholder" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPlaceholder</a>
