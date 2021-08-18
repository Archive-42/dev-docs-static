HTMLBaseFontElement
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLBaseFontElement` interface provides special properties (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating [`<basefont>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont) elements.

The `<basefont>` element has been deprecated in HTML4 and removed in HTML5. This latest specification requires that this element implements [`HTMLUnknownElement`](htmlunknownelement) rather than `HTMLBaseFontElement`.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLBaseFontElement.color`</span>  
Is a [`DOMString`](domstring) representing the text color using either a named color or a color specified in the hexadecimal `#RRGGBB` format.

<span class="page-not-created">`HTMLBaseFontElement.face`</span>  
Is a [`DOMString`](domstring) representing a list of one or more font names. The document text in the default style is rendered in the first font face that the client's browser supports. If no font listed is installed on the local system, the browser typically defaults to the proportional or fixed-width font for that system.

<span class="page-not-created">`HTMLBaseFontElement.size`</span>  
Is a [`DOMString`](domstring) representing the font size as either a numeric or relative value. Numeric values range from `1` to `7` with `1` being the smallest and `3` the default. Relative value starts with a `'+'` or a `'-`'.

Methods
-------

*No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-32774408">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLBaseFontElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-32774408">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLBaseFontElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLBaseFontElement`

No

12-79

1-4

5

No

1-10

No

No

No

No

1-10

No

`color`

No

17-79

1-4

5

No

1-10

No

No

No

No

1-10

No

`face`

No

12-79

1-4

5

No

1-10

No

No

No

No

1-10

No

`size`

No

12-79

1-4

5

No

1-10

No

No

No

No

1-10

No

See also
--------

-   The HTML element [`<basefont>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont) *was* implementing this interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement</a>
