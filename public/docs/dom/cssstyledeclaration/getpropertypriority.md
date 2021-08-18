# CSSStyleDeclaration.getPropertyPriority()

The **CSSStyleDeclaration.getPropertyPriority()** method interface returns a [`DOMString`](../domstring) that provides all explicitly set priorities on the CSS property.

## Syntax

    var priority = style.getPropertyPriority(property);

### Parameters

- _`property`_ is a [`DOMString`](../domstring) representing the property name to be checked.

### Return value

- `priority` is a [`DOMString`](../domstring) that represents the priority (e.g. `"important"`) if one exists. If none exists, returns the empty string.

## Example

The following JavaScript code checks whether `margin` is marked as important in a CSS selector rule:

    var declaration = document.styleSheets[0].cssRules[0].style;
    var isImportant = declaration.getPropertyPriority('margin') === 'important';

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-getpropertypriority">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.getPropertyPriority()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
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

`getPropertyPriority`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/getPropertyPriority" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/getPropertyPriority</a>
