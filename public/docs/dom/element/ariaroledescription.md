# Element.ariaRoleDescription

The `ariaRoleDescription` property of the [`Element`](../element) interface reflects the value of the `aria-roledescription` attribute, which defines a human-readable, author-localized description for the role of an element.

## Syntax

    var ariaRoleDescription = element.ariaRoleDescription;
    element.ariaRoleDescription = ariaRoleDescription

### Value

A [`DOMString`](../domstring).

## Examples

In this example the `aria-roledescription` attribute on the element with an ID of `myApplication` has been set. Using `ariaRoleDescription` we can update the value.

    <div id="myApplication" role="application" aria-roledescription="a description of this widget">...</div>

    let el = document.getElementById('myApplication');
    console.log(el.ariaRoleDescription); // "a description of this widget"
    el.ariaRoleDescription = "an updated description of this widget"
    console.log(el.ariaRoleDescription); // "an updated description of this widget"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaorientation">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaRoleDescription' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaRoleDescription`

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

- [ARIA: application role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Application_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRoleDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRoleDescription</a>
