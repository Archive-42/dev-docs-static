# Element.ariaDisabled

### Note

The `ariaDisabled` property of the [`Element`](../element) interface reflects the value of the `aria-disabled` attribute, which indicates that the element is perceivable but disabled, so it is not editable or otherwise operable.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="button"` or the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element as these have built in semantics and do not require ARIA attributes.

## Syntax

    var ariaDisabled = element.ariaDisabled;
    element.ariaDisabled = ariaDisabled

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The element is enabled.

`"false"`  
The element and all focusable descendants are disabled and its value cannot be changed by the user.

## Examples

In this example the `aria-disabled` attribute on the element with an ID of `saveChanges` is set to "true" indicating that this input is currently disabled. Using `ariaDisabled` we update the value to "false".

    <div id="saveChanges" tabindex="0" role="button" aria-disabled="true">Save</div>

    let el = document.getElementById('saveChanges');
    console.log(el.ariaDisabled); // "true"
    el.ariaDisabled = "false"
    console.log(el.ariaDisabled); // "false"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariadisabled">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaDisabled' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaDisabled`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDisabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDisabled</a>
