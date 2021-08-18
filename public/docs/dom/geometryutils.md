GeometryUtils
=============

The `GeometryUtils` interface provides utility methods to retrieve geometry information about [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) nodes.

`GeometryUtils` is a raw interface and no object of this type can be created; it is implemented by [`Text`](text), [`Element`](element), [`CSSPseudoElement`](csspseudoelement), and [`Document`](document) objects.

Properties
----------

*This interface does not implement any properties.*

Methods
-------

<span class="page-not-created">`GeometryUtils.getBoxQuads()`</span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

Returns a list of [`DOMQuad`](domquad) objects representing the CSS fragments of the node.

<span class="page-not-created">`GeometryUtils.convertQuadFromNode()`</span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<span class="page-not-created">`GeometryUtils.convertRectFromNode()`</span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<span class="page-not-created">`GeometryUtils.convertPointFromNode()`</span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#the-geometryutils-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'GeometryUtils' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`GeometryUtils`

?

?

31

?

?

?

?

?

31

?

?

?

`convertPointFromNode`

?

?

?

?

?

?

?

?

?

?

?

?

`convertQuadFromNode`

?

?

?

?

?

?

?

?

?

?

?

?

`convertRectFromNode`

?

?

?

?

?

?

?

?

?

?

?

?

`getBoxQuads`

?

?

31

?

?

?

?

?

31

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeometryUtils" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeometryUtils</a>
