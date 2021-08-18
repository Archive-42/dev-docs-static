# Element.ariaLevel

### Note

The `ariaLevel` property of the [`Element`](../element) interface reflects the value of the `aria-level` attribute, which defines the hierarchical level of an element within a structure.

Where possible use an HTML [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) or other correct heading level as these have built in semantics and do not require ARIA attributes.

## Syntax

    var ariaLevel = element.ariaLevel;
    element.ariaLevel = ariaLevel

### Value

A [`DOMString`](../domstring) containing an integer.

## Examples

In this example the `aria-level` attribute on the element with an ID of `main-heading` is set to "1". Using `ariaLevel` we update the value to "2".

    <div role="heading" id="main-heading" aria-level="1">This is a main page heading</div>

    let el = document.getElementById('main-heading');
    console.log(el.ariaLevel); // "1"
    el.ariaLevel = "2"
    console.log(el.ariaLevel); // "2"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-arialevel">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaLevel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaLevel`

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

- [ARIA: heading role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/heading_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLevel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLevel</a>
