# Document.rootElement

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`Document.rootElement` returns the [`Element`](../element) that is the root element of the [`document`](../document) if it is an [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element, otherwise `null`. It is deprecated in favor of [`Document.documentElement`](documentelement), which returns the root element for all documents.

## Syntax

    const element = document.rootElement

## Notes

If the document is a non-empty SVG document, then the `rootElement` will be an [`SVGSVGElement`](../svgsvgelement), identical to the `documentElement`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/struct.html#__svg__SVGDocument__rootElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGDocument.rootElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Deprecated</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/struct.html#__svg__SVGDocument__rootElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGDocument.rootElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement</a>
