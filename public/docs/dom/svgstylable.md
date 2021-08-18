SVGStylable
===========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `SVGStylable` interface is implemented on all objects corresponding to SVG elements that can have `style`, `class` and presentation attributes specified on them.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><ul><li><a href="cssvalue"><code>CSSValue</code></a> <code>getPresentationAttribute(in DOMString</code> name)</li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly <a href="svganimatedstring"><code>SVGAnimatedString</code></a> <code>className</code></li><li>readonly <a href="cssstyledeclaration"><code>CSSStyleDeclaration</code></a> <code>style</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGStylable">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>className</code></td><td><a href="svganimatedstring"><code>SVGAnimatedString</code></a></td><td>Corresponds to attribute <code>class</code> on the given element.</td></tr><tr class="even"><td><code>style</code></td><td><a href="cssstyledeclaration"><code>CSSStyleDeclaration</code></a></td><td>Corresponds to attribute <code>style</code> on the given element.</td></tr></tbody></table>

Methods
-------

<table><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>getPresentationAttribute(in DOMString</code> <em>name</em>)</td><td><a href="cssvalue"><code>CSSValue</code></a></td><td>Returns the base (i.e., static) value of a given presentation attribute as an object of type <a href="cssvalue"><code>CSSValue</code></a>. The returned object is live; changes to the objects represent immediate changes to the objects to which the <a href="cssvalue"><code>CSSValue</code></a> is attached.</td></tr></tbody></table>

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

`SVGStylable`

?

≤18

1.5-20

?

?

?

No

?

4-20

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGStylable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGStylable</a>
