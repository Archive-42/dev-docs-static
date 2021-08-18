HTMLHtmlElement
===============

The `HTMLHtmlElement` interface serves as the root node for a given HTML document. This object inherits the properties and methods described in the [`HTMLElement`](htmlelement) interface.

You can retrieve the `HTMLHtmlElement` object for a given document by reading the value of the [`document.documentElement`](document/documentelement) property.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

 [`HTMLHtmlElement.version`](htmlhtmlelement/version) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the version of the HTML Document Type Definition (DTD) that governs this document. This property should not be used any more as it is non-conforming. Omit it.

Methods
-------

*No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlhtmlelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHtmlElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/semantics.html#the-html-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLHtmlElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change since the last snapshot</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/semantics.html#the-html-element">HTML5<br />
<span class="small">The definition of 'HTMLHtmlElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <code>version</code> element has been removed, as it is non-conforming.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-33759296">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLHtmlElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Reflecting the element change in <a href="https://www.w3.org/TR/html401/">HTML 4.01 Specification</a>, the <code>version</code> property is now deprecated.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-33759296">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLHtmlElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLHtmlElement`

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

`version`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

See also
--------

-   HTML element implementing this interface: [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement</a>
