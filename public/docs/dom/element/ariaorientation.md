# Element.ariaOrientation

The `ariaOrientation` property of the [`Element`](../element) interface reflects the value of the [`aria-orientation`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-orientation_attribute) attribute, which indicates whether the element's orientation is horizontal, vertical, or unknown/ambiguous.

## Syntax

    var ariaOrientation = element.ariaOrientation;
    element.ariaOrientation = ariaOrientation

### Value

A [`DOMString`](../domstring) with one of the following values:

`"horizontal"`  
The element is horizontal.

`"vertical"`  
The element is vertical.

`"undefined"`  
The element's orientation is unknown.

## Examples

In this example the `aria-orientation` attribute on the element with an ID of `handle_zoomSlider` is set to "vertical". Using `ariaOrientation` we update the value to "horizontal".

    <a href="#" id="handle_zoomSlider"
      role="slider"
      aria-orientation="vertical"
      aria-valuemin="0"
      aria-valuemax="17"
      aria-valuenow="14" >
    <span>11</span>
    </a>

    let el = document.getElementById('handle_zoomSlider');
    console.log(el.ariaOrientation); // "vertical"
    el.ariaOrientation = "horizontal"
    console.log(el.ariaOrientation); // "horizontal"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaorientation">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaOrientation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaOrientation`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaOrientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaOrientation</a>
