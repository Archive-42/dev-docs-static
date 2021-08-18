# Element.ariaValueMax

The `ariaValueMax` property of the [`Element`](../element) interface reflects the value of the [`aria-valuemax`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-valuemax_attribute) attribute, which defines the maximum allowed value for a range widget.

## Syntax

    var ariaValueMax = element.ariaValueMax;
    element.ariaValueMax = ariaValueMax

### Value

A [`DOMString`](../domstring) which contains a number.

## Examples

In this example the `aria-valuemax` attribute on the element with an ID of `slider` is set to "7". Using `ariaValueMax` we update the value to "6".

    <div role="slider" aria-valuenow="1"
      aria-valuemin="1" aria-valuemax="7"
        aria-valuetext="Sunday">

    let el = document.getElementById('slider');
    console.log(el.ariaValueMax); // 7
    el.ariaValueMax = "6";
    console.log(el.ariaValueMax); // 6

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariavaluemax">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaValueMax' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaValueMax`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMax</a>
