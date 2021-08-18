# CSSStyleDeclaration.item()

## Syntax

    var propertyName = style.item(index);

### Parameters

- _`index`_ is the index of the node to be fetched. The index is zero-based.

### Return value

- _`propertyName`_ is a [`DOMString`](../domstring) that is the name of the CSS property at the specified index.

JavaScript has a special simpler syntax for obtaining an item from a NodeList by index:

    var propertyName = style[index];

## Example

    var style = document.getElementById('div1').style;
    var propertyName = style.item(1); // or style[1] - returns the second style listed

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-item">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.item()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
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

`item`

1

12

1

9

≤12.1

6

4.4

18

4

≤12.1

Yes

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/item</a>
