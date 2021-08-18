# Element.ariaModal

The `ariaModal` property of the [`Element`](../element) interface reflects the value of the `aria-modal` attribute, which indicates whether an element is modal when displayed.

## Syntax

    var ariaModal = element.ariaModal;
    element.ariaModal = ariaModal

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The element is modal.

`"false"`  
The element is not modal.

## Examples

In this example the `aria-modal` attribute on the element with an ID of `address-modal` is set to "true" indicating that this is a modal dialog. Using `ariaModal` we update the value to "false".

    <div role="dialog" id="address-modal" aria-labelledby="dialog1Title"
      aria-describedby="dialog1Desc" aria-modal="true"></div>

    let el = document.getElementById('address-modal');
    console.log(el.ariaModal); // "true"
    el.ariaModal = "false"
    console.log(el.ariaModal); // "false"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariamodal">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaModal' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaModal`

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

- [ARIA: dialog role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/dialog_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaModal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaModal</a>
