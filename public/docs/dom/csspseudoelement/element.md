# CSSPseudoElement.element

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `element` read-only property of the [`CSSPseudoElement`](../csspseudoelement) interface returns a reference to the originating element of the pseudo-element, in other words its parent element.

## Syntax

    var originatingElement = cssPseudoElement.element;

### Value

An [`Element`](../element) representing the pseudo-element's originating element.

## Examples

The example below demonstrates the relationship between `CSSPseudoElement.element` and <span class="page-not-created">`Element.pseudo()`</span>:

    const myElement = document.querySelector('q');
    const cssPseudoElement = myElement.pseudo('::after');
    const originatingElement = cssPseudoElement.element;

    console.log(myElement === originatingElement);                  // Outputs true
    console.log(myElement.parentElement === originatingElement);    // Outputs false
    console.log(myElement.lastElementChild === cssPseudoElement);   // Outputs false
    console.log(myElement.lastChild === cssPseudoElement);          // Outputs false
    console.log(myElement.nextElementSibling === cssPseudoElement); // Outputs false
    console.log(myElement.nextSibling === cssPseudoElement);        // Outputs false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#dom-csspseudoelement-element">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of 'element' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`element`

No

No

75

67-75

63-67

No

No

No

No

No

67-79

63-67

No

No

No

## See also

- <span class="page-not-created">`Element.pseudo()`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/element" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/element</a>
