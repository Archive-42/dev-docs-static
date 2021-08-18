# Element.ariaHidden

The `ariaHidden` property of the [`Element`](../element) interface reflects the value of the [`aria-hidden`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-hidden_attribute) attribute, which indicates whether the element is exposed to an accessibility API.

## Syntax

    var ariaHidden = element.ariaHidden;
    element.ariaHidden = ariaHidden

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The element is hidden from the accessibility API.

`"false"`  
The element is exposed to the accessibility API as if it were rendered.

`undefined`  
The element's hidden state is determined by the user agent based on whether it is rendered.

## Examples

In this example the `aria-hidden` attribute on the element with an ID of `hidden` is set to "true". Using `ariaHidden` we update the value to "false".

    <div id="hidden" aria-hidden="true">Some things are better left unsaid.</div>

    let el = document.getElementById('hidden');
    console.log(el.ariaHidden); // true
    el.ariaHidden = "false"
    console.log(el.ariaHidden); // false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariahidden">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaHidden' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaHidden`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHidden" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaHidden</a>
