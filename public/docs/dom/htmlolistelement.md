HTMLOListElement
================

The `HTMLOListElement` interface provides special properties (beyond those defined on the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating ordered list elements.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLOListElement.reversed`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value reflecting the [`reversed`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#attr-reversed) and defining if the numbering is descending, that is its value is `true`, or ascending (`false`).

<span class="page-not-created">`HTMLOListElement.start`</span>  
Is a `long` value reflecting the [`start`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#attr-start) and defining the value of the first number of the first element of the list.

<span class="page-not-created">`HTMLOListElement.type`</span>  
Is a [`DOMString`](domstring) value reflecting the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#attr-type) and defining the kind of marker to be used to display. It can have the following values:

-   `'1'` meaning that decimal numbers are used: `1`, `2`, `3`, `4`, `5`, …
-   `'a'` meaning that the lowercase latin alphabet is used: `a`, `b`, `c`, `d`, `e`, …
-   `'A'` meaning that the uppercase latin alphabet is used: `A`, `B`, `C`, `D`, `E`, …
-   `'i'` meaning that the lowercase latin numerals are used: `i`, `ii`, `iii`, `iv`, `v`, …
-   `'I'` meaning that the uppercase latin numerals are used: `I`, `II`, `III`, `IV`, `V`, …

 <span class="page-not-created">`HTMLOListElement.compact`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that spacing between list items should be reduced. This property reflects the [`compact`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol#attr-compact) attribute only, it doesn't consider the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) CSS property used for that behavior in modern pages.

Methods
-------

*No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlolistelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLOListElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-ol-element">HTML5<br />
<span class="small">The definition of 'HTMLOListElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <code>reversed</code> property.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-58056027">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLOListElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-58056027">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLOListElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`HTMLOListElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`compact`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`reversed`

18

79

18

No

≤12.1

6

≤37

Yes

18

≤12.1

6

Yes

`start`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`type`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   The HTML element implementing this interface: [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement</a>
