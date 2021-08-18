# HTMLLIElement

The `HTMLLIElement` interface exposes specific properties and methods (beyond those defined by regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating list elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLLIElement.type`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the type of the bullets, `"disc"`, `"square"` or `"circle"`. As the standard way of defining the list type is via the CSS [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property, use the CSSOM methods to set it via a script.

<span class="page-not-created">`HTMLLIElement.value`</span>  
Is a `long` indicating the ordinal position of the _list element_ inside a given [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol). It reflects the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li#attr-value) attribute of the HTML [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) element, and can be smaller than `0`. If the [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) element is not a child of an [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) element, the property has no meaning.

## Methods

_No specific method; inherits properties from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmllielement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLLIElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-li-element">HTML5<br />
<span class="small">The definition of 'HTMLLIElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following property is now obsolete: <code>type</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-74680021">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLLIElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-74680021">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLLIElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLLIElement`

1

12

1

Prior to Firefox 10, Gecko incorrectly reflected negative value attributes to 0.

5.5

≤12.1

1

1

18

4

Prior to Firefox 10, Gecko incorrectly reflected negative value attributes to 0.

≤12.1

1

1.0

`type`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`value`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The HTML element implementing this interface: [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement</a>
