# Element.ariaAtomic

The `ariaAtomic` property of the [`Element`](../element) interface reflects the value of the `aria-atomic` attribute, which indicates whether assistive technologies will present all, or only parts of, the changed region based on the change notifications defined by the <span class="page-not-created">`aria-relevant`</span> attribute.

## Syntax

    var ariaAtomic = element.ariaAtomic;
    element.ariaAtomic = ariaAtomic

### Value

A [`DOMString`](../domstring) with one of the following values:

`"false"`  
Assistive technologies will present only the changed node or nodes.

`"true"`  
Assistive technologies will present the entire changed region as a whole, including the author-defined label if one exists.

## Examples

In this example the `aria-atomic` attribute on the element with an ID of `"clock"` is set to "true". Using `ariaAtomic` we update the value to "false".

    <div id="clock" role="timer" aria-live="polite" aria-atomic="true"></div>

    let el = document.getElementById('clock');
    console.log(el.ariaAtomic); // true
    el.ariaAtomic = "false"
    console.log(el.ariaAtomic); // false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaatomic">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaAtomic' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaAtomic`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAtomic" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaAtomic</a>
