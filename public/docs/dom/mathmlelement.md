MathMLElement
=============

The `MathMLElement` interface represents any [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) element.

Properties
----------

*This interface has no properties, but inherits properties from: <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`Element`](element), [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement)*

Methods
-------

*This interface has no methods, but inherits methods from: <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`Element`](element), [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement)*

Examples
--------

### MathML

    <math xmlns="http://www.w3.org/1998/Math/MathML">
      <msqrt>
        <mi>x</mi>
      </msqrt>
    </math>

### JavaScript

    document.querySelector('msqrt').constructor.name; // MathMLElement

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://mathml-refresh.github.io/mathml-core/#dom-mathmlelement">MathMLElement interface</a></td><td></td><td></td></tr></tbody></table>

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

`MathMLElement`

No

No

71

No

No

No

No

No

No

No

No

No

See also
--------

-   [`Element`](element)
-   [`HTMLElement`](htmlelement)
-   [`SVGElement`](svgelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MathMLElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MathMLElement</a>
