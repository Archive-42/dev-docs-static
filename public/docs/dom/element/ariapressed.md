# Element.ariaPressed

### Note

The `ariaPressed` property of the [`Element`](../element) interface reflects the value of the `aria-pressed` attribute, which indicates the current "pressed" state of toggle buttons.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="button"` or the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element as these have built in semantics and do not require ARIA attributes.

## Syntax

    var ariaPressed = element.ariaPressed;
    element.ariaPressed = ariaPressed

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The element is pressed.

`"false"`  
The element supports being pressed but is not currently pressed.

`"mixed"`  
Indicates a mixed mode value for a tri-state toggle button.

`"undefined"`  
The element does not support being pressed.

## Examples

In this example the `aria-pressed` attribute on the element with an ID of `saveChanges` is set to "false" indicating that this input is currently not pressed. Using `ariaPressed` we update the value to "true".

    <div id="saveChanges" tabindex="0" role="button" aria-pressed="false">Save</div>

    let el = document.getElementById('saveChanges');
    console.log(el.ariaPressed); // "false"
    el.ariaPressed = "true"
    console.log(el.ariaPressed); // "true"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariapressed">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaPressed' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaPressed`

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

- [ARIA: button role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPressed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPressed</a>
