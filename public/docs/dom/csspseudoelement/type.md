# CSSPseudoElement.type

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `type` read-only property of the [`CSSPseudoElement`](../csspseudoelement) interface returns the type of the pseudo-element as a string, represented in the form of a [CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors#pseudo-elements).

## Syntax

    var typeOfPseudoElement = cssPseudoElement.type;

### Value

A [`CSSOMString`](../cssomstring) containing one of the following values:

- [`"::before"`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
- [`"::after"`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
- [`"::marker"`](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker)

## Examples

The example below demonstrates the relationship between `CSSPseudoElement.type` and <span class="page-not-created">`Element.pseudo()`</span>:

    const myElement = document.querySelector('q');
    const mySelector = '::after';
    const cssPseudoElement = myElement.pseudo(mySelector);
    const typeOfPseudoElement = cssPseudoElement.type;

    console.log(mySelector === typeOfPseudoElement); // Outputs true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#dom-csspseudoelement-type">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

No

No

75

63-75

No

No

No

No

No

63-79

No

No

No

## See also

- <span class="page-not-created">`Element.pseudo()`</span>
- [Index of standard pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements#index_of_standard_pseudo-elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/type</a>
