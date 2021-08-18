# Element.ariaDescription

The `ariaDescription` property of the [`Element`](../element) interface reflects the value of the `aria-description` attribute, which defines a string value that describes or annotates the current element.

## Syntax

    var ariaDescription = element.ariaDescription;
    element.ariaDescription = ariaDescription

### Value

A [`DOMString`](../domstring).

## Examples

In this example the `aria-description` attribute on the element with an ID of `close-button` is set to the string "A longer description of the function of this element". Using `ariaDescription` we can update the value.

    <button aria-label="Close" aria-description="A longer description of the function of this element" id="close-button">X</button>

    let el = document.getElementById('close-button');
    console.log(el.ariaDescription); // "A longer description of the function of this element"
    el.ariaDescription = "A different description"
    console.log(el.ariaDescription); // "A different description"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariadescription">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaDescription' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaDescription`

83

83

No

No

69

No

83

83

No

59

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaDescription</a>
