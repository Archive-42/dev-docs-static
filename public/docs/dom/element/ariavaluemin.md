# Element.ariaValueMin

The `ariaValueMin` property of the [`Element`](../element) interface reflects the value of the [`aria-valuemin`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-valuemin_attribute) attribute, which defines the minimum allowed value for a range widget.

## Syntax

    var ariaValueMin = element.ariaValueMin;
    element.ariaValueMin = ariaValueMin

### Value

A [`DOMString`](../domstring) which contains a number.

## Examples

In this example the `aria-valuemin` attribute on the element with an ID of `slider` is set to "1". Using `ariaValueMin` we update the value to "2".

    <div role="slider" aria-valuenow="1"
      aria-valuemin="1" aria-valuemax="7"
        aria-valuetext="Sunday">

    let el = document.getElementById('slider');
    console.log(el.ariaValueMin); // 1
    el.ariaValueMin = "2";
    console.log(el.ariaValueMin); // 2

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariavaluemin">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaValueMin' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaValueMin`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueMin</a>
