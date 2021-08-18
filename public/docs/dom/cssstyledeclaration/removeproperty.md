# CSSStyleDeclaration.removeProperty()

The `CSSStyleDeclaration.removeProperty()` method interface removes a property from a CSS style declaration object.

## Syntax

    var oldValue = style.removeProperty(property);

### Parameters

- _`property`_ is a [`DOMString`](../domstring) representing the property name to be removed. Note that multi-word property names are hyphenated and not camel-cased.

### Return value

- `oldValue` is a [`DOMString`](../domstring) equal to the value of the CSS property before it was removed.

### Exceptions

- [`DOMException`](../domexception) NO_MODIFICATION_ALLOWED_ERR: if the property or declaration block is read only.

## Example

The following JavaScript code removes the `background-color` CSS property from a selector rule:

    var declaration = document.styleSheets[0].rules[0].style;
    var oldValue = declaration.removeProperty('background-color');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-removeproperty">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.removeProperty()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`removeProperty`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/removeProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/removeProperty</a>
