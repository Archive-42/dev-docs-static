HTMLEmbedElement
================

The `HTMLEmbedElement` interface provides special properties (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) elements.

This topic describes the `HTMLEmbedElement` interface as defined in the standard. It does not address earlier, non-standardized version of the interface.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

 <span class="page-not-created">`HTMLEmbedElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing an enumerated property indicating alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, `"center"`, and `"justify"`.

<span class="page-not-created">`HTMLEmbedElement.height`</span>  
Is a [`DOMString`](domstring) reflecting the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed#attr-height) HTML attribute, containing the displayed height of the resource.

 <span class="page-not-created">`HTMLEmbedElement.name`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the name of the embedded object.

<span class="page-not-created">`HTMLEmbedElement.src`</span>  
Is a [`DOMString`](domstring) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed#attr-src) HTML attribute, containing the address of the resource.

<span class="page-not-created">`HTMLEmbedElement.type`</span>  
Is a [`DOMString`](domstring) that reflects the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed#attr-type) HTML attribute, containing the type of the resource.

<span class="page-not-created">`HTMLEmbedElement.width`</span>  
Is a [`DOMString`](domstring) that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed#attr-width) HTML attribute, containing the displayed width of the resource.

Methods
-------

*No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlembedelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLEmbedElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Adds two obsolete properties, <code>name</code> and <code>align</code>, to help with compatibility with old Web sites.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-embed-element">HTML5<br />
<span class="small">The definition of 'HTMLEmbedElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLEmbedElement`

1

Starting with Chrome 58, this interface can no longer be called as a function.

12

1

5.5

≤12.1

Starting with Opera 45, this interface can no longer be called as a function.

3

1

Starting with WebView 58, this interface can no longer be called as a function.

18

Starting with Chrome 58, this interface can no longer be called as a function.

4

≤12.1

Starting with Opera 45, this interface can no longer be called as a function.

1

1.0

Starting with Samsung Internet 7.0, this interface can no longer be called as a function.

`align`

1

79

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`getSVGDocument`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`height`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`name`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`src`

1

12

1

6

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

79

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`width`

1

12

1

6

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

-   The HTML element implementing this interface: [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement</a>
